QCarCamFrameInfo_t

QCarCamBufferList_t

QCarCamBuffer_t

QCarCamHndl_t



QCarCamFrameInfo_t

QCarCamHndl_t

QCarCamBufferList_t

QCarCamMode_t

QCarCamMode_t

QCarCamFrameInfo_t

QCarCamVendorParam_t

WQCarCamSetParam

WQCarCamGetParam

QCarCamFrameInfo_t



AisBufferList::AisBufferList(AisBuflistIdType id,

​    uint32 maxBuffers)

{

  m_id = id;

  m_maxBuffers = STD_MIN(maxBuffers, QCARCAM_MAX_NUM_BUFFERS);

  m_colorFmt = (qcarcam_color_fmt_t)0;

  m_width = 0;

  m_height = 0;

  m_nBuffers = 0;

  memset(m_pBuffers, 0x0, sizeof(m_pBuffers));

  m_GetFreeBuf = NULL;

  m_ReturnBuf = NULL;

  m_AllocBuf = NULL;

  m_mutex = NULL;

  m_bufferDoneQ = NULL;

  m_isBufferDoneQInit = FALSE;

};











┌─────────────────────────────────────────────────────────────────────────────────────────┐
│  PAL层抽象的高通QCarCam接口                                                      │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  高通QCarCam接口（底层）                                                      │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ QCarCam接口（高通提供的.so库）                                      │     │
│  │ - WQCarCamOpen(): 打开相机设备                                    │     │
│  │ - WQCarCamClose(): 关闭相机设备                                   │     │
│  │ - WQCarCamSetBuffers(): 设置缓冲区                                   │     │
│  │ - WQCarCamStart(): 启动流                                        │     │
│  │ - WQCarCamStop(): 停止流                                         │     │
│  │ - WQCarCamGetFrame(): 获取帧                                       │     │
│  │ - WQCarCamSetParam(): 设置参数                                       │     │
│  │ - WQCarCamGetParam(): 获取参数                                       │     │
│  │ - WQCarCamRegisterEventCallback(): 注册事件回调                         │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  PAL层抽象（中间层）                                                          │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ CameraDeviceImp: 设备管理抽象                                    │     │
│  │ - open(): 打开相机设备                                            │     │
│  │ - close(): 关闭相机设备                                           │     │
│  │ - getParameter(): 获取参数                                          │     │
│  │ - setParameter(): 设置参数                                           │     │
│  │ - queryParameter(): 查询参数                                        │     │
│  │ - getDeviceInfo(): 获取设备信息                                     │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ CameraStreamImp: 流控制抽象                                      │     │
│  │ - enableStream(): 启用流                                         │     │
│  │ - disableStream(): 禁用流                                        │     │
│  │ - reserveStream(): 保留流                                         │     │
│  │ - releaseStream(): 释放流                                         │     │
│  │ - SubmitAvailableBuffers(): 提交可用缓冲区                         │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ CameraBufferImp: 缓冲区管理抽象                                  │     │
│  │ - setBuffers(): 设置缓冲区                                         │     │
│  │ - requestBuffers(): 请求缓冲区                                     │     │
│  │ - releaseRequestedBuffers(): 释放请求的缓冲区                        │     │
│  │ - enqueueBuffer(): 入队缓冲区                                      │     │
│  │ - dequeueBuffer(): 出队缓冲区                                      │     │
│  │ - getFps(): 获取FPS                                              │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  应用层接口（上层）                                                              │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ CameraDevice: 统一的相机设备接口                                  │     │
│  │ - stream: IStream* (流控制接口)                                  │     │
│  │ - buffer: IBuffer* (缓冲区接口)                                  │     │
│  │ - parameter: IParameter* (参数接口)                                │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────────────────┘



// pal_camera/inc/PALCameraDeviceImp.h

class CameraDeviceImp : public CameraDevice {
public:
    // ========== 1. 设备管理接口 ==========
    
    // 打开相机设备
    // 对应QCarCam: WQCarCamOpen()
    ReturnVal open(OpenFlags flags) override;
    
    // 关闭相机设备
    // 对应QCarCam: WQCarCamClose()
    ReturnVal close() override;
    
    // 获取设备ID
    InputDeviceId getDeviceId() const override;
    
    // 获取端口ID
    PortId getPortId() const override;
    
    // 获取型号ID
    CameraModelId getModelId() const override;
    
    // 获取相机类型
    std::string getCameraType() const { return _cameraType; }
    
    // 获取部件号
    std::string getPartNumber() const { return _cameraPartNumber; }
    
    // ========== 2. 参数管理接口 ==========
    
    // 获取参数
    // 对应QCarCam: WQCarCamGetParam()
    ReturnVal getParameter(PAL_INOUT ControlParameter &param) override;
    
    // 设置参数
    // 对应QCarCam: WQCarCamSetParam()
    ReturnVal setParameter(const ControlParameter &param, ReceiptCookie &receiptCookie) override;
    
    // 查询参数
    // 对应QCarCam: WQCarCamQueryParam()
    ReturnVal queryParameter(const ControlParameter &param, PAL_OUT ControlParameterDescriptor &descriptor) override;
    
    // 获取设备信息
    // 对应QCarCam: WQCarCamGetDeviceInfo()
    ReturnVal getDeviceInfo(PAL_OUT DeviceInfo &info) override;
    
    // ========== 3. 流控制接口 ==========
    
    // 流控制接口
    IStream* stream = nullptr;
    
    // ========== 4. 缓冲区管理接口 ==========
    
    // 缓冲区管理接口
    IBuffer* buffer = nullptr;
    
    // ========== 5. 参数管理接口 ==========
    
    // 参数管理接口
    IParameter* parameter = nullptr;

private:
    // QCarCam句柄
    QCarCamHndl_t qcm_handler = QCARCAM_HNDL_INVALID;
    
    // QCarCam输入描述符
    uint32_t qcm_input_desc = QCARCAM_INPUT_MAX;
    
    // 设备映射
    DeviceMapping deviceMapping;
    
    // 相机部件号
    std::string _cameraPartNumber;
    
    // 相机类型
    std::string _cameraType;
};



// pal_camera/inc/PALCameraStreamImp.h

class CameraStreamImp : public Singleton<CameraStreamImp>
                      , public TStream<CameraDeviceImp>
{
public:
    // ========== 1. 启用流 ==========
    // 对应QCarCam: WQCarCamStart()
    ReturnVal enableStream(CameraDeviceImp *device, SelectMetadata selectMetadata = SELECT_METADATA_DEFAULT);

    // ========== 2. 禁用流 ==========
    // 对应QCarCam: WQCarCamStop()
    ReturnVal disableStream(CameraDeviceImp *device);
    
    // ========== 3. 保留流 ==========
    // 对应QCarCam: WQCarCamReserve()
    ReturnVal reserveStream(CameraDeviceImp *device);
    
    // ========== 4. 释放流 ==========
    // 对应QCarCam: WQCarCamRelease()
    ReturnVal releaseStream(CameraDeviceImp *device);
    
    // ========== 5. 提交可用缓冲区 ==========
    // 对应QCarCam: WQCarCamSubmitRequest()
    ReturnVal SubmitAvailableBuffers(CameraDeviceImp *device);
    
    // ========== 6. 准备请求 ==========
    // 对应QCarCam: WQCarCamSubmitRequest()
    ReturnVal prepareRequest(CameraDeviceImp *device, QCarCamRequest_t& request);
};



// pal_camera/inc/PALCameraBufferImp.h

class CameraBufferImp : public Singleton<CameraBufferImp>
                      , public TBuffer<CameraDeviceImp>
{
public:
    // ========== 1. 设置缓冲区 ==========
    // 对应QCarCam: WQCarCamSetBuffers()
    ReturnVal setBuffers(CameraDeviceImp *device, FrameBufferGroup& buffers);

    // ========== 2. 请求缓冲区 ==========
    // 对应QCarCam: WQCarCamRequestBuffers()
    ReturnVal requestBuffers(CameraDeviceImp *device, PAL_OUT FrameBufferGroup& buffers);
    
    // ========== 3. 释放请求的缓冲区 ==========
    // 对应QCarCam: WQCarCamReleaseBuffers()
    ReturnVal releaseRequestedBuffers(CameraDeviceImp *device, FrameBufferGroup& buffers);
    
    // ========== 4. 入队缓冲区 ==========
    // 对应QCarCam: WQCarCamEnqueueBuffer()
    ReturnVal enqueueBuffer(CameraDeviceImp *device, FrameBufferDescriptor& descriptor);
    
    // ========== 5. 出队缓冲区 ==========
    // 对应QCarCam: WQCarCamGetFrame()
    ReturnVal dequeueBuffer(CameraDeviceImp *device, PAL_OUT FrameBufferDescriptor*& descriptor,
                         TimeMilliseconds timeoutMS);
    
    // ========== 6. 获取FPS ==========
    // 对应QCarCam: WQCarCamGetFps()
    ReturnVal getFps(CameraDeviceImp *device, PAL_OUT double &fps);
};



┌─────────────────────────────────────────────────────────────────────────────────────────┐
│  嵌入行解析功能                                                              │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  高通QCarCam接口：                                                              │
│  - 只提供原始的嵌入行数据                                                      │
│  - 不提供解析功能                                                             │
│  - 应用层需要自己解析嵌入行数据                                                 │
│                                                                             │
│  PAL层增强：                                                                  │
│  - 提供完整的嵌入行解析框架                                                   │
│  - 支持多种相机型号的嵌入行解析                                               │
│  - 使用工厂模式创建解析器                                                     │
│  - 使用策略模式解析不同参数                                                   │
│                                                                             │
│  架构设计：                                                                  │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ IEmbededlineParserManager (解析器管理器接口)                      │     │
│  │ - createDeviceParser(): 创建设备解析器                             │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ EmbededlineParserManager (解析器管理器实现)                      │     │
│  │ - 单例模式                                                       │     │
│  │ - 管理所有设备解析器                                               │     │
│  │ - 根据相机类型创建解析器                                             │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ IDeviceEmbedlineParser (设备解析器接口)                         │     │
│  │ - parseAll(): 解析所有参数                                       │     │
│  │ - getStreamSourceID(): 获取流源ID                                │     │
│  │ - getFrameCounter(): 获取帧计数器                                │     │
│  │ - getMetaData(): 获取元数据                                      │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ DeviceEmbedlineParser (设备解析器基类)                           │     │
│  │ - parseAll(): 解析所有参数                                       │     │
│  │ - getStreamSourceID(): 获取流源ID                                │     │
│  │ - getFrameCounter(): 获取帧计数器                                │     │
│  │ - getMetaData(): 获取元数据                                      │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ IEmbededlineParamParser (参数解析器接口)                         │     │
│  │ - parse(): 解析参数                                              │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ EmbededlineParamParser (参数解析器基类)                         │     │
│  │ - parse(): 解析参数                                              │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ 具体参数解析器：                                                      │     │
│  │ - BasicEmbededlineParser: 基础参数解析器                        │     │
│  │ - Basic10bEmbededlineParser: 10位基础参数解析器                 │     │
│  │ - BooleanParser: 布尔值解析器                                  │     │
│  │ - BooleanParser8Bit: 8位布尔值解析器                             │     │
│  │ - ROIYUVParser: ROI YUV解析器                                   │     │
│  │ - ROIHistParser: ROI直方图解析器                                │     │
│  │ - ROIWindowParser: ROI窗口解析器                                 │     │
│  │ - VoltageParser: 电压解析器                                     │     │
│  │ - MirrorParser: 镜像解析器                                     │     │
│  │ - GainParser4Patac: Patac增益解析器                           │     │
│  │ - TempParser4AR: AR温度解析器                                   │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────────────────┘



┌─────────────────────────────────────────────────────────────────────────────────────────┐
│  参数管理功能                                                                  │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  高通QCarCam接口：                                                              │
│  - 只提供基本的参数设置/获取接口                                             │
│  - 参数类型有限                                                             │
│  - 不支持参数验证                                                           │
│  - 不支持参数通知                                                           │
│                                                                             │
│  PAL层增强：                                                                  │
│  - 提供完整的参数管理框架                                                   │
│  - 支持多种参数类型                                                         │
│  - 支持参数验证                                                           │
│  - 支持参数通知                                                           │
│  - 支持参数动作注册                                                       │
│                                                                             │
│  架构设计：                                                                  │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ IParameter (参数接口)                                           │     │
│  │ - getParameter(): 获取参数                                        │     │
│  │ - setParameter(): 设置参数                                        │     │
│  │ - queryParameter(): 查询参数                                     │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ TParameter<CameraDeviceImp> (参数模板类)                       │     │
│  │ - getParameter(): 获取参数                                        │     │
│  │ - setParameter(): 设置参数                                        │     │
│  │ - queryParameter(): 查询参数                                     │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ ParamAction (参数动作基类)                                    │     │
│  │ - RegisterGetParamHandler(): 注册获取参数处理器                     │     │
│  │ - RegisterSetParamHandler(): 注册设置参数处理器                     │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ GetParamAction (获取参数动作)                                  │     │
│  │ - run(): 执行获取参数                                         │     │
│  │ - handlePixelFormat(): 处理像素格式                              │     │
│  │ - handleColorSpace(): 处理色彩空间                              │     │
│  │ - handleResolutionWidth(): 处理分辨率宽度                        │     │
│  │ - handleResolutionHeight(): 处理分辨率高度                       │     │
│  │ - handleBrightness(): 处理亮度                                  │     │
│  │ - handleFsinPeriod(): 处理帧同步周期                            │     │
│  │ - handleIRLedSwitch(): 处理红外LED开关                         │     │
│  │ - handleGAMMA(): 处理伽马                                    │     │
│  │ - handleAutoWhiteBalance(): 处理自动白平衡                       │     │
│  │ - handleAutoExposure(): 处理自动曝光                            │     │
│  │ - handleHDREnable(): 处理HDR启用                              │     │
│  │ - handleFrameRateMode(): 处理帧率模式                           │     │
│  │ - handleHorizontalFocalLength(): 处理水平焦距                    │     │
│  │ - handleVerticalFocalLength(): 处理垂直焦距                      │     │
│  │ - handleNumEmbeddedLinesTopRows(): 处理顶部嵌入行数               │     │
│  │ - handleNumEmbeddedLinesBottomRows(): 处理底部嵌入行数            │     │
│  │ - handleTempSensor1(): 处理温度传感器1                          │     │
│  │ - handleTempSensor2(): 处理温度传感器2                          │     │
│  │ - handleCameraMode(): 处理相机模式                              │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ SetParamAction (设置参数动作)                                  │     │
│  │ - run(): 执行设置参数                                         │     │
│  │ - handleGAMMA(): 处理伽马                                    │     │
│  │ - handleFSinPeriod(): 处理帧同步周期                            │     │
│  │ - handleIRLedSwitch(): 处理红外LED开关                         │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────────────────┘



┌─────────────────────────────────────────────────────────────────────────────────────────┐
│  参数管理功能                                                                  │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  高通QCarCam接口：                                                              │
│  - 只提供基本的参数设置/获取接口                                             │
│  - 参数类型有限                                                             │
│  - 不支持参数验证                                                           │
│  - 不支持参数通知                                                           │
│                                                                             │
│  PAL层增强：                                                                  │
│  - 提供完整的参数管理框架                                                   │
│  - 支持多种参数类型                                                         │
│  - 支持参数验证                                                           │
│  - 支持参数通知                                                           │
│  - 支持参数动作注册                                                       │
│                                                                             │
│  架构设计：                                                                  │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ IParameter (参数接口)                                           │     │
│  │ - getParameter(): 获取参数                                        │     │
│  │ - setParameter(): 设置参数                                        │     │
│  │ - queryParameter(): 查询参数                                     │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ TParameter<CameraDeviceImp> (参数模板类)                       │     │
│  │ - getParameter(): 获取参数                                        │     │
│  │ - setParameter(): 设置参数                                        │     │
│  │ - queryParameter(): 查询参数                                     │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ ParamAction (参数动作基类)                                    │     │
│  │ - RegisterGetParamHandler(): 注册获取参数处理器                     │     │
│  │ - RegisterSetParamHandler(): 注册设置参数处理器                     │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ GetParamAction (获取参数动作)                                  │     │
│  │ - run(): 执行获取参数                                         │     │
│  │ - handlePixelFormat(): 处理像素格式                              │     │
│  │ - handleColorSpace(): 处理色彩空间                              │     │
│  │ - handleResolutionWidth(): 处理分辨率宽度                        │     │
│  │ - handleResolutionHeight(): 处理分辨率高度                       │     │
│  │ - handleBrightness(): 处理亮度                                  │     │
│  │ - handleFsinPeriod(): 处理帧同步周期                            │     │
│  │ - handleIRLedSwitch(): 处理红外LED开关                         │     │
│  │ - handleGAMMA(): 处理伽马                                    │     │
│  │ - handleAutoWhiteBalance(): 处理自动白平衡                       │     │
│  │ - handleAutoExposure(): 处理自动曝光                            │     │
│  │ - handleHDREnable(): 处理HDR启用                              │     │
│  │ - handleFrameRateMode(): 处理帧率模式                           │     │
│  │ - handleHorizontalFocalLength(): 处理水平焦距                    │     │
│  │ - handleVerticalFocalLength(): 处理垂直焦距                      │     │
│  │ - handleNumEmbeddedLinesTopRows(): 处理顶部嵌入行数               │     │
│  │ - handleNumEmbeddedLinesBottomRows(): 处理底部嵌入行数            │     │
│  │ - handleTempSensor1(): 处理温度传感器1                          │     │
│  │ - handleTempSensor2(): 处理温度传感器2                          │     │
│  │ - handleCameraMode(): 处理相机模式                              │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ SetParamAction (设置参数动作)                                  │     │
│  │ - run(): 执行设置参数                                         │     │
│  │ - handleGAMMA(): 处理伽马                                    │     │
│  │ - handleFSinPeriod(): 处理帧同步周期                            │     │
│  │ - handleIRLedSwitch(): 处理红外LED开关                         │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────────────────┘





┌─────────────────────────────────────────────────────────────────────────────────────────┐
│  事件处理功能                                                                  │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  高通QCarCam接口：                                                              │
│  - 提供基本的事件回调接口                                                     │
│  - 事件类型有限                                                             │
│  - 不提供事件分发                                                           │
│  - 不提供事件过滤                                                           │
│                                                                             │
│  PAL层增强：                                                                  │
│  - 提供完整的事件处理框架                                                   │
│  - 支持多种事件类型                                                         │
│  - 支持事件分发                                                           │
│  - 支持事件过滤                                                           │
│  - 支持事件通知                                                           │
│                                                                             │
│  架构设计：                                                                  │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ CameraEventHandler (事件处理器)                                │     │
│  │ - registQCarcamCallback(): 注册QCarCam回调                      │     │
│  │ - unregistQCarcamCallback(): 注销QCarCam回调                    │     │
│  │ - handle_QCARCAM_EVENT_FRAME_READY(): 处理帧就绪事件           │     │
│  │ - handle_QCARCAM_EVENT_INPUT_SIGNAL(): 处理输入信号事件          │     │
│  │ - handle_QCARCAM_EVENT_ERROR(): 处理错误事件                     │     │
│  │ - handle_QCARCAM_EVENT_VENDOR(): 处理厂商事件                   │     │
│  │ - handle_QCARCAM_EVENT_FRAME_FREEZE(): 处理帧冻结事件           │     │
│  │ - handle_QCARCAM_EVENT_CONTROL_PARAMETER_CHANGED(): 处理参数变化事件 │     │
│  │ - notify(DiagnosticsNotification, bool): 通知诊断事件          │     │
│  │ - notify(ErrorNotification): 通知错误事件                    │     │
│  │ - reset(): 重置事件处理器                                        │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ 事件类型：                                                              │     │
│  │ - QCARCAM_EVENT_FRAME_READY: 帧就绪事件                      │     │
│  │ - QCARCAM_EVENT_INPUT_SIGNAL: 输入信号事件                    │     │
│  │ - QCARCAM_EVENT_ERROR: 错误事件                               │     │
│  │ - QCARCAM_EVENT_VENDOR: 厂商事件                             │     │
│  │ - QCARCAM_EVENT_FRAME_FREEZE: 帧冻结事件                       │     │
│  │ - QCARCAM_EVENT_CONTROL_PARAMETER_CHANGED: 参数变化事件          │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ 事件通知：                                                              │     │
│  │ - DiagnosticsNotifier: 诊断通知器                             │     │
│  │ - WriteNotifier: 写入通知器                                  │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────────────────┘



┌─────────────────────────────────────────────────────────────────────────────────────────┐
│  相机仲裁功能                                                                  │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  高通QCarCam接口：                                                              │
│  - 支持多客户端模式                                                         │
│  - 不提供仲裁功能                                                           │
│  - 不提供权限管理                                                           │
│                                                                             │
│  PAL层增强：                                                                  │
│  - 提供完整的相机仲裁框架                                                   │
│  - 支持多种仲裁类型                                                         │
│  - 支持权限管理                                                           │
│  - 支持虚拟通道                                                           │
│                                                                             │
│  架构设计：                                                                  │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ CameraArbitrationApi (相机仲裁API接口)                       │     │
│  │ - getArbitrationType(): 获取仲裁类型                             │     │
│  │ - requestAccess(): 请求访问                                     │     │
│  │ - releaseAccess(): 释放访问                                     │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ 仲裁类型：                                                              │     │
│  │ - DIRECT_FULL_ACCESS: 直接完全访问                             │     │
│  │ - VIRTUAL_CHANNEL_ACCESS: 虚拟通道访问                     │     │
│  │ - MULTI_CLIENT_ACCESS: 多客户端访问                           │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ CameraDeviceImp中的仲裁功能：                                        │     │
│  │ - cameraArbitrationApi: 相机仲裁API指针                    │     │
│  │ - getArbitration(): 获取仲裁类型                                │     │
│  │ - enableBistMode(): 启用BIST模式                               │     │
│  │ - disableBistMode(): 禁用BIST模式                              │     │
│  │ - getBistModeResult(): 获取BIST模式结果                         │     │
│  │ - autoBistTest(): 自动BIST测试                                 │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────────────────┘



// pal_camera/inc/PALCameraDeviceImp.h

// ========== 1. 提交请求结构 ==========
struct SubmitRequest
{
    SubmitRequest();
    
    // 请求ID
    uint32_t requestId = 0;
    
    // 互斥锁
    std::mutex mtx;
    
    // 条件变量
    std::unique_ptr<IConditionVariable> cv;
    
    // 帧信息
    QCarCamFrameInfo_t frameInfo = {0};
    
    // 帧是否就绪
    bool isFrameReady = false;
};

// ========== 2. 相机流数据 ==========
struct CameraStreamData{
    // 缓冲区像素格式
    int bufferPixelFmt = 0;
    
    // 缓冲区宽度
    int bufferWidth = 0;
    
    // 缓冲区高度
    int bufferHeight = 0;
    
    // 缓冲区步长
    int bufferStride = 0;
    
    // 缓冲区大小
    size_t bufferSize = 0;
    
    // 顶部嵌入行数
    uint32_t numTopEmbeddedLines = 0;
    
    // 底部嵌入行数
    uint32_t numBottomEmbeddedLines = 0;
    
    // 请求缓冲区索引
    uint32_t requestBufferIdx = 0;
    
    // QCarCam释放缓冲区偏移
    uint32_t qcm_release_buffer_offset = 0;
    
    // QCarCam缓冲区列表
    QCarCamBufferList_t qcm_buffers = {};
    
    // QCarCam缓冲区数组
    QCarCamBuffer_t qcarcam_buffers[PAL_MAX_NUM_BUFFERS] = {0};
    
    // 工作帧缓冲区组
    FrameBufferGroup *workingFrameBufferGroup = nullptr;
    
    // 请求的帧缓冲区组
    FrameBufferGroup *requestedFrameBufferGroup = nullptr;
};

// ========== 3. 相机流 ==========
struct CameraStream {
    // 是否冻结帧
    bool isFrozenFrame = false;
    
    // 是否启用
    bool enabled = false;
    
    // 是否保留
    bool reserved = false;
    
    // 是否等待第一帧出队
    bool isPendingFirstFrameDequeue = true;
    
    // 是否等待第一帧入队
    bool isPendingFirstFrameEnqueue = true;
    
    // 客户端ID
    ClientID clientId = 0;
    
    // 流源ID
    uint32_t streamSourceId = 0;
    
    // 帧率
    float fps = 30.f;
    
    // 帧计数
    uint32_t frameCount = 0;
    
    // 前一帧计数器
    uint32_t preFrameCounter = 0;
    
    // QCarCam句柄
    QCarCamHndl_t qcm_handler = QCARCAM_HNDL_INVALID;
    
    // QCarCam输入描述符
    uint32_t qcm_input_desc = QCARCAM_INPUT_MAX;
    
    // 定义每帧中设置的元数据
    SelectMetadata selectMetadata = SELECT_METADATA_DEFAULT;
    
    // 流数量（默认只有1个流）
    uint32_t streamCount = 1;
    
    // 流数据数组
    CameraStreamData streamData[MAX_SUPPORTED_STREAM_INFO] = {};
    
    // 提交请求
    SubmitRequest submitRequest;
    
    // 缓冲区分配器
    PmemClientBufferAlloctor bufferAlloctor;
};

// ========== 4. 相机元数据 ==========
struct CameraMetaData{
    ~CameraMetaData(){
        Release();
    }

    // 通用元数据缓冲区
    QCarCamBufferList_t com_metadata_buffers = {};
    QCarCamBuffer_t qc_com_metadata_buffers[PAL_METADATA_NUM_BUFFERS] = {0};
    PmemClientBufferAlloctor comMetaAlloctor;
    void* pComMetaBuf[PAL_METADATA_NUM_BUFFERS] = {nullptr};
    
    // 输入元数据缓冲区
    QCarCamBufferList_t in_metadata_buffers = {};
    QCarCamBuffer_t qc_in_metadata_buffers[PAL_METADATA_NUM_BUFFERS] = {0};
    PmemClientBufferAlloctor inMetaAlloctor;
    void* pInMetaBuf[PAL_METADATA_NUM_BUFFERS] = {nullptr};
    
    // 输出元数据缓冲区
    QCarCamBufferList_t out_metadata_buffers = {};
    QCarCamBuffer_t qc_out_metadata_buffers[PAL_METADATA_NUM_BUFFERS] = {0};
    PmemClientBufferAlloctor outMetaAlloctor;
    void* pOutMetaBuf[PAL_METADATA_NUM_BUFFERS] = {nullptr};
    
    // 流元数据缓冲区
    QCarCamBufferList_t stream_metadata_buffers = {};
    QCarCamBuffer_t qc_stream_metadata_buffers[PAL_METADATA_NUM_BUFFERS] = {0};
    PmemClientBufferAlloctor streamMetaAlloctor;
    void* pStreamMetaBuf[PAL_METADATA_NUM_BUFFERS] = {nullptr};
    
    // 释放元数据缓冲区
    void Release(){
        ReleaseMetaBuf(com_metadata_buffers, comMetaAlloctor, pComMetaBuf);
        ReleaseMetaBuf(in_metadata_buffers, inMetaAlloctor, pInMetaBuf);
        ReleaseMetaBuf(out_metadata_buffers, outMetaAlloctor, pOutMetaBuf);
        ReleaseMetaBuf(stream_metadata_buffers, streamMetaAlloctor, pStreamMetaBuf);
    }
    
    // 释放元数据缓冲区
    void ReleaseMetaBuf(QCarCamBufferList_t& metaBufferList, 
                       PmemClientBufferAlloctor& memAlloc, void** pMetaBuf){
        for (uint32_t index = 0; index < metaBufferList.nBuffers; index++)
        {
            auto pBuf = pMetaBuf[index];
            if (pBuf)
            {
                memAlloc.free(pBuf);
            }
        }
    }
};





┌─────────────────────────────────────────────────────────────────────────────────────────┐
│  工厂模式                                                                    │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  高通QCarCam接口：                                                              │
│  - 不提供工厂模式                                                           │
│                                                                             │
│  PAL层增强：                                                                  │
│  - 提供完整的工厂模式框架                                                   │
│  - 支持设备解析器工厂                                                     │
│  - 支持参数解析器工厂                                                     │
│  - 支持动态创建                                                           │
│                                                                             │
│  架构设计：                                                                  │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ IFactory (工厂接口)                                            │     │
│  │ - setConfigs(): 设置配置                                      │     │
│  │ - create(): 创建对象                                          │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ DeviceEmbedlineParserFactory (设备解析器工厂)                 │     │
│  │ - setConfigs(): 设置配置                                      │     │
│  │ - create(): 创建设备解析器                                  │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ EmbededlineParserManager (解析器管理器)                      │     │
│  │ - createDeviceParser(): 创建设备解析器                         │     │
│  │ - 单例模式                                                       │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────────────────┘



┌─────────────────────────────────────────────────────────────────────────────────────────┐
│  单例模式                                                                    │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  高通QCarCam接口：                                                              │
│  - 不提供单例模式                                                           │
│                                                                             │
│  PAL层增强：                                                                  │
│  - 提供完整的单例模式框架                                                   │
│  - 支持线程安全                                                           │
│  - 支持延迟初始化                                                         │
│                                                                             │
│  架构设计：                                                                  │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ Singleton<T> (单例模板类)                                   │     │
│  │ - instance(): 获取单例实例                                  │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                              │                                                   │
│                              ▼                                                   │
│  ┌──────────────────────────────────────────────────────────────────────────┐     │
│  │ 单例类：                                                              │     │
│  │ - CameraStreamImp: 流控制单例                                │     │
│  │ - CameraBufferImp: 缓冲区管理单例                           │     │
│  │ - EmbededlineParserManager: 解析器管理器单例                  │     │
│  │ - CameraLoggerManager: 日志管理器单例                         │     │
│  └──────────────────────────────────────────────────────────────────────────┘     │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────────────────┘



### 4.1 PAL层抽象的高通QCarCam接口

| QCarCam接口                     | PAL层抽象                                   | 功能描述     |
| ------------------------------- | ------------------------------------------- | ------------ |
| WQCarCamOpen()                  | CameraDeviceImp::open()                     | 打开相机设备 |
| WQCarCamClose()                 | CameraDeviceImp::close()                    | 关闭相机设备 |
| WQCarCamSetBuffers()            | CameraBufferImp::setBuffers()               | 设置缓冲区   |
| WQCarCamStart()                 | CameraStreamImp::enableStream()             | 启动流       |
| WQCarCamStop()                  | CameraStreamImp::disableStream()            | 停止流       |
| WQCarCamGetFrame()              | CameraBufferImp::dequeueBuffer()            | 获取帧       |
| WQCarCamSetParam()              | CameraDeviceImp::setParameter()             | 设置参数     |
| WQCarCamGetParam()              | CameraDeviceImp::getParameter()             | 获取参数     |
| WQCarCamQueryParam()            | CameraDeviceImp::queryParameter()           | 查询参数     |
| WQCarCamRegisterEventCallback() | CameraEventHandler::registQCarcamCallback() | 注册事件回调 |

### 4.2 在QCarCam接口基础上实现/增强的功能

| 功能模块         | 增强内容                                  | 实现方式              |
| ---------------- | ----------------------------------------- | --------------------- |
| **嵌入行解析**   | 提供完整的嵌入行解析框架                  | 工厂模式 + 策略模式   |
| **参数管理**     | 支持多种参数类型、参数验证、参数通知      | 动作注册 + 映射表     |
| **事件处理**     | 支持多种事件类型、事件分发、事件过滤      | 事件处理器 + 回调函数 |
| **诊断通知**     | 支持多种诊断类型、状态缓存、订阅/取消订阅 | 观察者模式 + 状态缓存 |
| **相机仲裁**     | 支持多种仲裁类型、权限管理、虚拟通道      | 仲裁API + 虚拟通道    |
| **多客户端支持** | 支持客户端ID管理、请求管理、缓冲区管理    | 客户端ID + 请求队列   |

### 4.3 除了QCarCam接口之外实现的其他功能

| 功能模块       | 实现内容                                     | 设计模式            |
| -------------- | -------------------------------------------- | ------------------- |
| **日志系统**   | 多种日志级别、多种日志输出、日志过滤         | 单例模式 + 策略模式 |
| **工厂模式**   | 设备解析器工厂、参数解析器工厂               | 工厂模式            |
| **单例模式**   | 流控制单例、缓冲区管理单例、解析器管理器单例 | 单例模式            |
| **模板化接口** | 泛型接口、类型安全                           | 模板编程            |

### 4.4 面试回答建议



"PAL层对高通QCarCam接口的抽象以及实现/增强的功能：

**1. PAL层抽象的高通QCarCam接口**：

- CameraDeviceImp

  : 抽象了QCarCam的设备管理接口

  - open(): 对应WQCarCamOpen()
  - close(): 对应WQCarCamClose()
  - getParameter(): 对应WQCarCamGetParam()
  - setParameter(): 对应WQCarCamSetParam()
  - queryParameter(): 对应WQCarCamQueryParam()

- CameraStreamImp

  : 抽象了QCarCam的流控制接口

  - enableStream(): 对应WQCarCamStart()
  - disableStream(): 对应WQCarCamStop()
  - reserveStream(): 对应WQCarCamReserve()
  - releaseStream(): 对应WQCarCamRelease()

- CameraBufferImp

  : 抽象了QCarCam的缓冲区管理接口

  - setBuffers(): 对应WQCarCamSetBuffers()
  - requestBuffers(): 对应WQCarCamRequestBuffers()
  - enqueueBuffer(): 对应WQCarCamEnqueueBuffer()
  - dequeueBuffer(): 对应WQCarCamGetFrame()

**2. 在QCarCam接口基础上实现/增强的功能**：

- 嵌入行解析功能

  ：

  - 高通QCarCam只提供原始的嵌入行数据，不提供解析功能
  - PAL层提供完整的嵌入行解析框架，支持多种相机型号的嵌入行解析
  - 使用工厂模式创建解析器，使用策略模式解析不同参数
  - 支持的参数解析器：BasicEmbededlineParser、BooleanParser、ROIYUVParser、VoltageParser等

- 参数管理功能

  ：

  - 高通QCarCam只提供基本的参数设置/获取接口，参数类型有限
  - PAL层提供完整的参数管理框架，支持多种参数类型
  - 支持参数验证、参数通知、参数动作注册
  - 支持的参数类型：像素格式、色彩空间、分辨率、亮度、伽马、自动白平衡、自动曝光、HDR、帧率、焦距、温度等

- 事件处理功能

  ：

  - 高通QCarCam只提供基本的事件回调接口，事件类型有限
  - PAL层提供完整的事件处理框架，支持多种事件类型
  - 支持事件分发、事件过滤、事件通知
  - 支持的事件类型：帧就绪、输入信号、错误、厂商、帧冻结、参数变化等

- 诊断通知功能

  ：

  - 高通QCarCam只提供基本的错误事件，不提供诊断通知
  - PAL层提供完整的诊断通知框架，支持多种诊断类型
  - 支持状态缓存、订阅/取消订阅、状态查询
  - 支持的诊断类型：信号无效、冻结帧、相机断开、相机电源供应等

- 相机仲裁功能

  ：

  - 高通QCarCam支持多客户端模式，但不提供仲裁功能
  - PAL层提供完整的相机仲裁框架，支持多种仲裁类型
  - 支持权限管理、虚拟通道、BIST模式
  - 支持的仲裁类型：DIRECT_FULL_ACCESS、VIRTUAL_CHANNEL_ACCESS、MULTI_CLIENT_ACCESS

- 多客户端支持

  ：

  - 高通QCarCam支持多客户端模式，需要客户端自己管理
  - PAL层提供完整的多客户端管理框架
  - 支持客户端ID管理、请求管理、缓冲区管理
  - 支持多流、多元数据缓冲区

**3. 除了QCarCam接口之外实现的其他功能**：

- 日志系统

  ：

  - 提供完整的日志框架，支持多种日志级别
  - 支持多种日志输出：控制台、Slog、文件
  - 支持日志过滤

- 工厂模式

  ：

  - 提供完整的工厂模式框架
  - 支持设备解析器工厂、参数解析器工厂
  - 支持动态创建

- 单例模式

  ：

  - 提供完整的单例模式框架
  - 支持线程安全、延迟初始化
  - 单例类：CameraStreamImp、CameraBufferImp、EmbededlineParserManager等

- 模板化接口

  ：

  - 提供泛型接口，类型安全

  - TStream

    、TBuffer

    等

    

**4. 设计模式应用**：

- **工厂模式**：创建设备解析器、参数解析器
- **策略模式**：解析不同类型的参数
- **观察者模式**：诊断通知、参数通知
- **单例模式**：流控制、缓冲区管理、解析器管理
- **模板编程**：泛型接口、类型安全"