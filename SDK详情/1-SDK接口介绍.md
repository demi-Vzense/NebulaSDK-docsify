# SDK接口介绍

## 1 Enum数据类型

### 1.1  VzFrameType

**功能：**

图像类型。

**PS:**不同型号产品对应的枚举值个数可能不同，请以具体型号文件夹下定义为准。

**枚举值：**

VzDepthFrame：表示深度图像类型

VzIRFrame：表示灰度图像类型

VzColorFrame：表示彩色图像类型

VzTransformColorImgToDepthSensorFrame：表示映射到深度传感器空间的彩色图像类型

VzTransformDepthImgToColorSensorFrame：表示映射到彩色传感器空间的深度图像类型

VzConfidenceFrame：表示激光强度图像

### 1.2  VzPixelFormat

**功能：

图像数据的像素类型。

**PS:**不同型号产品对应的枚举值个数可能不同，请以具体型号文件夹下定义为准。

**枚举值：**

VzPixelFormatDepthMM16：表示每个像素数据为16位的深度值，单位为毫米

VzPixelFormatGray8：表示每个像素数据为8位的灰度值

VzPixelFormatRGB888：表示每个像素数据为24位的RGB值

VzPixelFormatBGR888：表示每个像素数据为24位的BGR值

### 1.3  VzSensorType

**功能：**
传感器类型
**PS:**不同型号产品对应的枚举值个数可能不同，请以具体型号文件夹下定义为准。
**枚举值：**
VzToFSensor：表示深度数据传感器
VzColorSensor：表示彩色图像传感器

### 1.4  VzReturnStatus

**功能：**
接口函数的返回值。
**PS:**不同型号产品对应的枚举值个数可能不同，请以Include中具体型号文件夹下定义为准。
**枚举值：**
VzRetOK：表示调用成功
VzRetNoDeviceConnected：表示当前无设备连接
VzRetInvalidDeviceIndex：表示传入的设备序号无效
VzRetDevicePointerIsNull：表示传入的设备指针为空
VzRetInvalidFrameType：表示传入的图像类型无效
VzRetFramePointerIsNull：表示传入的图像指针为空
VzRetNoPropertyValueGet：表示无法获取当前属性值
VzRetNoPropertyValueSet：表示无法设置当前属性值
VzRetPropertyPointerIsNull：表示传入的指向存储属性值的缓存指针为空
VzRetPropertySizeNotEnough：表示传入的指向存储属性值的缓存空间不足
VzRetInvalidDepthRange：表示传入的depth range无效
VzRetGetFrameReadyTimeOut：表示获取图像时超时
VzRetInputPointerIsNull：表示传入的指针为空
VzRetCameraNotOpened：表示相机未打开
vzRetInvalidCameraType：表示传入的相机类型无效
VzRetInvalidParams：表示传入的参数无效
VzRetCurrentVersionNotSupport：表示当前版本不支持
VzRetUpgradeImgError：表示升级相机固件失败
VzRetUpgradeImgPathTooLong：表示传入的相机固件路径长度太长
VzRetUpgradeCallbackNotSet：表示未设置相机升级时的回调函数
VzRetNoAdapterConnected：表示电源适配器未连接
VzRetReInitialized：表示重复初始化
VzRetNoInitialized：表示未做初始化
VzRetCameraOpened：表示相机已经打开
VzRetCmdError：表示命令下发失败
VzRetCmdSyncTimeOut：表示命令发送成功，但是同步匹配失败
VzRetIPNotMatch：表示相机IP与主机IP不在同一网段
VzRetNotStopStream：表示未打开数据流
VzRetOthers：表示其他错误

### 1.5  VzConnectStatus

**功能：**
设备连接状态。
**PS:**不同型号产品对应的枚举值个数可能不同，请以Include中具体型号文件夹下定义为准。
**枚举值：**
VzConnectUNKNOWN：表示连接状态未知
VzUnconnected：表示设备未连接
VzConnected：表示设备已连接
VzOpened：表示设备已被打开
VzUpgradeUnconnected：表示设备处于升级待连接状态
VzUpgradeConnected：表示设备处于升级状态且已连接

### 1.6  VzWorkMode

**功能：**
设备工作状态。
**枚举值：**
VzActiveMode：表示设备处于主动工作状态。此时使用API打开相机后，设备会主动上传图像数据。
VzHardwareTriggerMode：表示设备处于被动工作状态。此时使用API打开相机后，设备在硬件触发的时候，才会上传图像数据。
VzSoftwareTriggerMode：表示设备处于被动工作状态。此时使用API打开相机后，设备在软件触发的时候，才会上传图像数据。

### 1.7  VzExposureControlMode

**功能：**
传感器的曝光模式。
**枚举值：**
VzExposureControlMode_Auto：表示传感器使用自动曝光模式
VzExposureControlMode_Manual：表示传感器使用手动曝光模式

## 2 Struct数据类型

### 2.1  VzRGB888Pixel

**功能：**
彩色图像像素类型RGB888。
**PS:**不同型号产品可能不支持RGB，如DCAM550，请以Include中具体型号文件夹下定义为准。
**成员：**
uint8_t r：表示红色通道
uint8_t g：表示绿色通道
uint8_t b：表示蓝色通道

### 2.2  VzBGR888Pixel

**功能：**
彩色图像像素类型BGR888。
**PS:**不同型号产品可能不支持RGB，如DCAM550，请以Include中具体型号文件夹下定义为准。
**成员：**
uint8_t b：表示蓝色通道
uint8_t g：表示绿色通道
uint8_t r：表示红色通道

### 2.3  VzVector3f

**功能：**
3维点坐标，单位为毫米。
**成员：**
float x：表示X轴方向的坐标值
float y：表示Y轴方向的坐标值
float z：表示Z轴方向的坐标值

### 2.4  VzVector2u16

**功能：**
2维点坐标。
**成员：**
float x：表示X轴方向的坐标值
float y：表示Y轴方向的坐标值

### 2.5  VzDepthVector3

**功能：**
深度图像的像素点表示。
**成员：**
int depthX：表示图像坐标系下，X轴方向的坐标值
int depthY：表示图像坐标系下，Y轴方向的坐标值
VzDepthPixel depthZ：表示像素坐标（depthX，depthY）处的深度值，单位为毫米

### 2.6  VzSensorIntrinsicParameters

**功能：**
传感器的镜头内参和畸变参数。内参通常用于点云的计算，畸变参数用于图像反畸变算法使用。
SDK 中已经实现深度图像到点云的转换及图像反畸变的功能，请参考例程使用相关接口。
**成员：**
        double	fx：Focal length x (pixel)
        double	fy：Focal length y (pixel)
        double	cx：Principal point x (pixel)
        double	cy：Principal point y (pixel)
        double	k1：Radial distortion coefficient, 1st-order
        double	k2：Radial distortion coefficient, 2nd-order
        double	p1：Tangential distortion coefficient
        double	p2：Tangential distortion coefficient
        double	k3：Radial distortion coefficient, 3rd-order
        double	k4：Radial distortion coefficient, 4st-order
        double	k5：Radial distortion coefficient, 5nd-order
        double	k6：Radial distortion coefficient, 6rd-order

### 2.7  VzSensorExtrinsicParameters

**功能：**
相机外参R 与T，用于depth 与rgb 图像的对齐，参考公式如下:
![](https://cdn.nlark.com/yuque/0/2023/png/36047038/1685172304496-ab013368-5ed6-40e1-b08f-c3eac636f3fb.png#averageHue=%23f1f1f1&id=MboGy&originHeight=210&originWidth=884&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
**成员：**
double rotation[9]：3×3 的旋转矩阵
double translation[3]：3×1 平移矩阵

### 2.8  VzFrame

**功能：**
图像信息
**成员：**
uint32_t       frameIndex：表示图像帧索引号
VzFrameType    frameType：表示图像数据类型
VzPixelFormat  pixelFormat：表示像素类型
uint8_t*       pFrameData：表示指向图像数据缓存的指针
uint32_t       dataLen：表示图像数据的长度，单位为字节
float          exposureTime：表示曝光时间，单位为微秒
uint8_t        depthRange：表示当前帧的深度范围，仅对深度图像有效
uint16_t       width：表示图像宽度
uint16_t       height：表示图像高度
uint64_t       deviceTimestamp：表示图像时间戳

### 2.9  VzFrameReady

**功能：**
图像数据是否就绪（1代表就绪，0代表未就绪）
**成员：**
uint32_t depth : 1：表示深度图像数据是否就绪
uint32_t ir : 1：表示灰度图像数据是否就绪
uint32_t color : 1：表示彩色图像数据是否就绪
uint32_t transformedColor : 1：表示对齐到深度传感器空间的彩色图像是否就绪
uint32_t transformedDepth : 1：表示对齐到彩色传感器空间的深度图像是否就绪
uint32_t confidence : 1：表示激光强度图像数据是否就绪
uint32_t reserved : 26：：预留位 

### 2.10 VzDeviceInfo

**功能：**
设备信息
**成员：**
int SessionCount：表示设备中有几个深度传感器
VzDeviceType devicetype：表示设备类型
char uri[256]：表示设备的标识符
char alias[64]：表示设备的别名
char serialNumber[64]：表示设备的序列号
char ip[17]：表示设备的IP地址
VzConnectStatus status：表示设备连接状态

### 2.11 VzConfidenceFilterParams

**功能：**
置信度滤波参数

**成员：**
bool enable：表示滤波是否打开，true代表打开，false代表关闭
int threshold：表示滤波阈值

### 2.12 VzFlyingPixelFilterParams

**功能：**
去飞点滤波参数
**成员：**
bool enable：表示滤波是否打开，true代表打开，false代表关闭
int threshold：表示滤波阈值

### 2.13 VzSpatialFilterParams

**功能：**
空间滤波参数。
**成员：**
bool enable：表示滤波是否打开，true代表打开，false代表关闭
int validCount：表示滤波计算时使用的参考点个数
int threshold：表示滤波阈值
int doCount：表示滤波执行几遍 

### 2.14 VzFillHoleFilterParams

**功能:**
补洞滤波参数
**成员:**
bool enable：表示滤波是否打开，true代表打开，false代表关闭
int validCount：表示滤波计算时使用的参考点个数
int threshold：表示滤波阈值
int doCount：表示滤波执行几遍

### 2.15 VzExposureTimeParams

**功能：**
传感器曝光参数
**成员：**
VzExposureControlMode mode：表示传感器曝光类型
int exposureTime：表示传感器曝光时间，单位微秒

## 3  API介绍

### 3.1  VZ_Initialize

**函数原型：**

<span id="VZ_Initialize">VzReturnStatus VZ_Initialize()</span>

**函数功能：**

完成SDK初始化，需要在调用其他API之前先调用

**函数参数：**

无

**返回值：**

VzRetOK：调用成功

其他值：调用失败

### 3.2  VZ_Shutdown

**函数原型：**

 <span id="VZ_Shutdown">VzReturnStatus VZ_Shutdown()</span>

**函数功能：**

完成SDK注销，释放SDK使用过程中创建的所有资源。该接口调用之后，不应调用除VZ_Initialize之外的其他接口

**函数参数：**

无

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.3  VZ_GetSDKVersion

**函数原型：**

<span id="VZ_GetSDKVersion">const char* VZ_GetSDKVersion()</span>

**函数功能：**

获取SDK的版本号：x.x.x

**函数参数：**

无

**返回值:**

SDK版本号

### 3.4  VZ_GetDeviceCount

**函数原型：**

<span id="VZ_GetDeviceCount">VzReturnStatus VZ_GetDeviceCount(uint32_t* pDeviceCount)</span>

**函数功能：**

获取已连接的设备数目

**函数参数：**

uint32_t* pDeviceCount：返回已连接的设备数目

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.5  VZ_GetDeviceInfo

**函数原型：

<span id="VZ_GetDeviceInfo">VzReturnStatus VZ_GetDeviceInfo(uint32_t deviceIndex, VzDeviceInfo* 	pDevicesInfo)</span>

**函数功能：**

获取指定索引号的设备信息

**函数参数：**

uint32_t deviceIndex：设备索引号

VzDeviceInfo* pDevicesInfo：返回设备信息

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.6  VZ_GetDeviceInfoList

**函数原型：

<span id="VZ_GetDeviceInfoList">VzReturnStatus VZ_GetDeviceInfoList(uint32_t deviceCount, VzDeviceInfo* 	pDevicesInfoList)</span>

**函数功能：**

获取deviceCount个数的设备信息列表

**函数参数：**

uint32_t deviceCount：需要获取信息列表的设备个数

VzDeviceInfo* pDevicesInfo：返回设备信息列表，其应该指向大小为	

sizeof(VzDeviceInfo)*deviceCount大小的缓存

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.7  VZ_OpenDeviceByUri

**函数原型：**

<span id="VZ_OpenDeviceByUri">VzReturnStatus VZ_OpenDeviceByUri(const char* pURI, VzDeviceHandle* 	pDevice)</span>

**函数功能：**

使用设备标识符打开设备

**函数参数：**

const char* pURI：设备标识符

VzDeviceHandle* pDevice： 打开设备成功后，返回的设备句柄

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.8  <span id="VZ_OpenDeviceByAlias">VZ_OpenDeviceByAlias</span>

**函数原型：**

VzReturnStatus VZ_OpenDeviceByAlias(const char* pAlias, 	VzDeviceHandle* 	pDevice)

**函数功能：**

使用设备别名打开设备

**函数参数：**

const char* pAlias：设备别名

VzDeviceHandle* pDevice： 打开设备成功后，返回的设备句柄

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.9  <span id="VZ_OpenDeviceByIP">VZ_OpenDeviceByIP</span>

**函数原型：**

VzReturnStatus VZ_OpenDeviceByIP(const char* pIP, VzDeviceHandle* 	pDevice)

**函数功能：**

使用设备IP地址打开设备

**函数参数：**

const char* pIP：设备的IP地址

VzDeviceHandle* pDevice： 打开设备成功后，返回的设备句柄

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.10  <span id="VZ_CloseDevice">VZ_CloseDevice</span>

**函数原型：

VzReturnStatus VZ_CloseDevice(VzDeviceHandle* pDevice)

**函数功能：**

关闭设备

**函数参数：**

VzDeviceHandle* pDevice： 要关闭设备的句柄

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.11  <span id="VZ_StartStream">VZ_StartStream</span>

**函数原型：

VzReturnStatus VZ_StartStream(VzDeviceHandle device)

**函数功能：**

打开数据流

**函数参数：**

VzDeviceHandle device： 要关闭数据流的设备的句柄

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.12  <span id="VZ_StopStream">VZ_StopStream</span>

**函数原型：

VzReturnStatus VZ_StopStream(VzDeviceHandle device)

**函数功能：**

关闭数据流

**函数参数：**

VzDeviceHandle device： 要关闭数据流的设备的句柄

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.13  <span id="VZ_GetFrameReady">VZ_GetFrameReady</span>

**函数原型：

VzReturnStatus VZ_GetFrameReady(VzDeviceHandle device, uint16_t 	waitTime, 

VzFrameReady* pFrameReady)

**函数功能：**

获取图像就绪状态。调用函数VZ_GetFrame前必须调用此函数，否则无法获取图像。

**函数参数：**

VzDeviceHandle device： 设备句柄

uint16_t waitTime：允许等待图像就绪的超时时间(ms)。此值与图像的帧率有关，建议值设置为2*1000/fps。例如当前的帧率为20，则建议设置waitTime为2 * 1000 / 20 = 100。如果设置waitTime为40，则调用函数时可能返回VzRetGetFrameReadyTimeOut。

VzFrameReady* pFrameReady：返回图像的就绪状态

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.14  <span id="VZ_GetFrame">VZ_GetFrame</span>

**函数原型：

VzReturnStatus VZ_GetFrame(VzDeviceHandle device, VzFrameType 	frameType, VzFrame* pVzFrame)

**函数功能：**

获取指定图像类型的图像数据。调用此函数前必须调用VZ_GetFrameReady。

**函数参数：**

VzDeviceHandle device： 设备句柄

VzFrameType frameType：待获取图像的类型

VzFrame* pVzFrame：返回的图像数据

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.15 <span id="VZ_SetWorkMode"> VZ_SetWorkMode</span>

**函数原型：

VzReturnStatus VZ_SetWorkMode(VzDeviceHandle device, VzWorkMode 	mode)

**函数功能：**

设置相机的工作模式

**函数参数：**

VzDeviceHandle device： 设备句柄

VzWorkMode mode：要设置的工作模式

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.16  <span id="VZ_GetWorkMode">VZ_GetWorkMode</span>

**函数原型：**

VzReturnStatus VZ_GetWorkMode(VzDeviceHandle device, VzWorkMode* 	pMode)

**函数功能：**

获取相机的工作模式

**函数参数：**

VzDeviceHandle device： 设备句柄

VzWorkMode* pMode：获取到的设备的工作模式

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.17  <span id="VZ_SetSoftwareSlaveTrigger">VZ_SetSoftwareSlaveTrigger</span>

**函数原型：

VzReturnStatus VZ_SetSoftwareSlaveTrigger(VzDeviceHandle device)

**函数功能：**

执行一次软件触发，仅当相机处于VzSoftwareTriggerMode时有效

**函数参数：**

VzDeviceHandle device： 设备句柄

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.18  <span id="VZ_GetSensorIntrinsicParameters">VZ_GetSensorIntrinsicParameters</span>

**函数原型：**

VzReturnStatus VZ_GetSensorIntrinsicParameters(VzDeviceHandle device, 	VzSensorType sensorType, VzSensorIntrinsicParameters* 		pSensorIntrinsicParameters)

**函数功能：

获取传感器镜头的内参

**函数参数：

VzDeviceHandle device： 设备句柄

VzSensorType sensorType：传感器类型

VzSensorIntrinsicParameters* pSensorIntrinsicParameters：返回传感器镜头的内参

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.19  <span id="VZ_GetSensorExtrinsicParameters">VZ_GetSensorExtrinsicParameters</span>

**函数原型：

VzReturnStatus VZ_GetSensorExtrinsicParameters(VzDeviceHandle device, 	VzSensorExtrinsicParameters* pSensorExtrinsicParameters)

**函数功能：**

获取设备的外参

**函数参数：**

VzDeviceHandle device： 设备句柄

VzSensorExtrinsicParameters* pSensorExtrinsicParameters：返回设备的外参
**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.20  <span id="VZ_GetFirmwareVersion">VZ_GetFirmwareVersion</span>

**函数原型：

VzReturnStatus VZ_GetFirmwareVersion(VzDeviceHandle device, char* 	pFirmwareVersion, int length)

**函数功能：**

获取设备的固件版本

**函数参数：**

VzDeviceHandle device： 设备句柄

char* pFirmwareVersion：返回设备的固件版本

int length：pFirmwareVersion指向的缓存的字节长度

**返回值:**

VzRetOK：调用成功

其他值：调用失败

### 3.21  <span id="VZ_GetDeviceMACAddress">VZ_GetDeviceMACAddress</span>

**函数原型：**
VzReturnStatus VZ_GetDeviceMACAddress(VzDeviceHandle device, char* 	pMACAddress)
**函数功能：**
获取设备的MAC地址
**函数参数：**
VzDeviceHandle device： 设备句柄
char* pMACAddress：返回设备的MAC地址，其默认是一个字节长度为18，以‘\0’结尾的字符串
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.22  <span id="VZ_SetIRGMMGain">VZ_SetIRGMMGain</span>

**函数原型：**
VzReturnStatus VZ_SetIRGMMGain(VzDeviceHandle device, uint8_t 	gmmgain)
**函数功能：**
设置IR图像的数字增益
**函数参数：**
VzDeviceHandle device： 设备句柄
uint8_t gmmgain：要设置给设备的IR增益值
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.23  <span id="VZ_GetIRGMMGain">VZ_GetIRGMMGain</span>

**函数原型：**
VzReturnStatus VZ_GetIRGMMGain(VzDeviceHandle device, uint8_t* 		pGmmgain)
**函数功能：**
获取IR图像的数字增益
**函数参数：**
VzDeviceHandle device： 设备句柄
uint8_t* pGmmgain：返回设备的IR增益值
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.24  <span id="VZ_SetColorPixelFormat">VZ_SetColorPixelFormat</span>

**函数原型：**
VzReturnStatus VZ_SetColorPixelFormat(VzDeviceHandle device, 	VzPixelFormat pixelFormat)
**函数功能：**
设置彩色图像的像素格式
**函数参数：**
VzDeviceHandle device： 设备句柄
VzPixelFormat pixelFormat：要设置的彩色图像的像素格式
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.25  <span id="VZ_SetColorResolution">VZ_SetColorResolution</span>

**函数原型：**
VzReturnStatus VZ_SetColorResolution(VzDeviceHandle device, int w, int h)
**函数功能：**
设置彩色图像的分辨率
**函数参数：**
VzDeviceHandle device： 设备句柄
int w：图像的宽
int h：图像的高
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.26  <span id="VZ_GetColorResolution">VZ_GetColorResolution</span>

**函数原型：**
VzReturnStatus VZ_GetColorResolution(VzDeviceHandle device, int* pW, int* pH)
**函数功能：**
获取彩色图像的分辨率
**函数参数：**
VzDeviceHandle device： 设备句柄
int* pW：返回彩色图像的图像宽
int* pH：返回彩色图像的图像高
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.27  <span id="VZ_SetFrameRate">VZ_SetFrameRate</span>

**函数原型：**
VzReturnStatus VZ_SetFrameRate(VzDeviceHandle device, int value)
**函数功能：**
设置设备的图像帧率，同时对深度和彩色图像生效。此接口是同步接口，耗时较长，大约需要500ms
**函数参数：**
VzDeviceHandle device： 设备句柄
 int value：要设置的目标帧率
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.28  <span id="VZ_GetFrameRate">VZ_GetFrameRate</span>

**函数原型：**
VzReturnStatus VZ_GetFrameRate(VzDeviceHandle device, int* pValue)
**函数功能：**
获取设备的图像帧率
**函数参数：**
VzDeviceHandle device： 设备句柄
int* pValue：返回设备的图像帧率
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.29  <span id="VZ_SetExposureControlMode">VZ_SetExposureControlMode</span>

**函数原型：**
VzReturnStatus VZ_SetExposureControlMode(VzDeviceHandle device, 	VzSensorType sensorType, VzExposureControlMode controlMode)
**函数功能：**
设置传感器的曝光模式
**函数参数：**
VzDeviceHandle device： 设备句柄
VzSensorType sensorType：要设置曝光模式的传感器类型
VzExposureControlMode controlMode：要设置的曝光模式
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.30  <span id="VZ_GetExposureControlMode">VZ_GetExposureControlMode</span>

**函数原型：**
VzReturnStatus VZ_GetExposureControlMode(VzDeviceHandle device, 		VzSensorType sensorType, VzExposureControlMode* pControlMode)
**函数功能：**
获取传感器的曝光模式
**函数参数：**
VzDeviceHandle device： 设备句柄
VzSensorType sensorType：要获取曝光模式的传感器类型
VzExposureControlMode controlMode：返回传感器的曝光模式
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.31  <span id="VZ_SetExposureTime">VZ_SetExposureTime</span>

**函数原型：**
VzReturnStatus VZ_SetExposureTime(VzDeviceHandle device, 	VzSensorType 	sensorType, VzExposureTimeParams exposureTime)
**函数功能：**
设置传感器的曝光时间
深度传感器，只支持在手动曝光模式下，设置曝光时间
彩色传感器，支持在自动曝光模式下，设置最大曝光时间；支持在手动曝光模式下，设置曝光时间
**函数参数：**
VzDeviceHandle device： 设备句柄
VzSensorType sensorType：要获取曝光时间的传感器类型
VzExposureTimeParams exposureTime：要设置的曝光时间参数

**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.32  <span id="VZ_GetExposureTime">VZ_GetExposureTime</span>

**函数原型：**
VzReturnStatus VZ_GetExposureTime(VzDeviceHandle device, 	VzSensorType 	sensorType, VzExposureTimeParams* pExposureTime)
**函数功能：**
获取传感器的曝光时间
深度传感器，支持在手动曝光模式下，获取曝光时间；支持获取最大曝光时间
彩色传感器，支持在手动曝光模式下，获取曝光时间；支持获取最大曝光时间
**函数参数：**
VzDeviceHandle device： 设备句柄
VzSensorType sensorType：要获取曝光时间的传感器类型
VzExposureTimeParams* pExposureTime：返回获取的曝光时间参数
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.33  <span id="VZ_SetTimeFilterEnabled">VZ_SetTimeFilterEnabled</span>

**函数原型：**
VzReturnStatus VZ_SetTimeFilterEnabled(VzDeviceHandle device, bool 	bEnabled)
**函数功能：**
设置深度图像的时域滤波开关
**函数参数：**
VzDeviceHandle device： 设备句柄
bool bEnabled：true表示滤波打开，false表示滤波关闭
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.34  <span id="VZ_GetTimeFilterEnabled">VZ_GetTimeFilterEnabled</span>

**函数原型：**
VzReturnStatus VZ_GetTimeFilterEnabled(VzDeviceHandle device, bool 	*pEnabled)
**函数功能：**
获取深度图像的时域滤波开关状态
**函数参数：**
VzDeviceHandle device： 设备句柄
bool *pEnabled：返回滤波开关状态
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.35  <span id="VZ_SetConfidenceFilterParams">VZ_SetConfidenceFilterParams</span>

**函数原型：**
VzReturnStatus VZ_SetConfidenceFilterParams(VzDeviceHandle device, 	VzConfidenceFilterParams params)
**函数功能：**
设置深度图像的置信度滤波参数
VzDeviceHandle device： 设备句柄
bool *pEnabled：返回滤波开关状态

**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.36  <span id="VZ_GetConfidenceFilterParams">VZ_GetConfidenceFilterParams</span>

**函数原型：**
VzReturnStatus VZ_GetConfidenceFilterParams(VzDeviceHandle device, 	VzConfidenceFilterParams *pParams)
**函数功能：**
获取深度图像的置信度滤波参数
**函数参数：**
VzDeviceHandle device： 设备句柄
bool *pEnabled：返回滤波开关状态
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.37  <span id="VZ_SetFlyingPixelFilterParams">VZ_SetFlyingPixelFilterParams</span>

**函数原型：**
VzReturnStatus VZ_SetFlyingPixelFilterParams(VzDeviceHandle device, 	const 	VzFlyingPixelFilterParams params)
**函数功能：**
设置深度图像的去飞点滤波参数
**函数参数：**
VzDeviceHandle device： 设备句柄
const VzFlyingPixelFilterParams params：滤波参数
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.38  <span id="VZ_GetFlyingPixelFilterParams">VZ_GetFlyingPixelFilterParams</span>

**函数原型：**
VzReturnStatus VZ_GetFlyingPixelFilterParams(VzDeviceHandle device, 	VzFlyingPixelFilterParams* params)

**函数功能：**
获取深度图像的去飞点滤波参数
**函数参数：**
VzDeviceHandle device： 设备句柄
VzFlyingPixelFilterParams* params：滤波参数
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.39  <span id="VZ_SetFillHoleFilterParams">VZ_SetFillHoleFilterParams</span>

**函数原型：**
VzReturnStatus VZ_SetFillHoleFilterParams(VzDeviceHandle device, const 	VzFillHoleFilterParams params)
**函数功能：**
设置深度图像的补洞滤波参数
**函数参数：**
VzDeviceHandle device： 设备句柄
const VzFillHoleFilterParams params：滤波参数
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.40  <span id="VZ_GetFillHoleFilterParams">VZ_GetFillHoleFilterParams</span>

**函数原型：**
VzReturnStatus VZ_GetFillHoleFilterParams(VzDeviceHandle device, 	VzFillHoleFilterParams* params)
**函数功能：**
获取深度图像的补洞滤波参数
**函数参数：**
VzDeviceHandle device： 设备句柄
VzFillHoleFilterParams* params：获取的滤波参数
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.41  <span id="VZ_SetSpatialFilterParams">VZ_SetSpatialFilterParams</span>

**函数原型：**
VzReturnStatus VZ_SetSpatialFilterParams(VzDeviceHandle device, const 	VzSpatialFilterParams params)
**函数功能：**
设置深度图像的空间滤波参数
**函数参数：**
VzDeviceHandle device： 设备句柄
const VzSpatialFilterParams params：滤波参数
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.42 <span id="VZ_GetSpatialFilterParams"> VZ_GetSpatialFilterParams</span>

**函数原型：**
VzReturnStatus VZ_GetSpatialFilterParams(VzDeviceHandle device, 	VzSpatialFilterParams* params)
**函数功能：**
设置深度图像的空间滤波参数

**函数参数：**
VzDeviceHandle device： 设备句柄
VzSpatialFilterParams* params：获取的滤波参数
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.43  <span id="VZ_SetTransformColorImgToDepthSensorEnabled">VZ_SetTransformColorImgToDepthSensorEnabled</span>

**函数原型：**
VzReturnStatus 	VZ_SetTransformColorImgToDepthSensorEnabled(VzDeviceHandle device, 	bool bEnabled)
**函数功能：**
设置彩色图像对齐到深度相机空间的开关，只有带彩色传感器的设备才支持此操作。如果打开开关，则调用VZ_GetFrameReady时，VzFrameReady.transformedColor的值为1，然后调用VZ_GetFrame可以得到VzTransformColorImgToDepthSensorFrame类型的彩色图像，其大小与深度图像大小相同。
**函数参数：**
VzDeviceHandle device：设备句柄
bool bEnabled：true打开对齐，false关闭对齐
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.44  <span id="VZ_GetTransformColorImgToDepthSensorEnabled">VZ_GetTransformColorImgToDepthSensorEnabled</span>

**函数原型：**
VzReturnStatus 	VZ_GetTransformColorImgToDepthSensorEnabled(VzDeviceHandle device, 	bool *bEnabled)
**函数功能：**
获取彩色图像对齐到深度相机空间的开关状态
**函数参数：**
VzDeviceHandle device： 设备句柄
bool *bEnabled：返回开关状态

**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.45  <span id="VZ_SetTransformDepthImgToColorSensorEnabled">VZ_SetTransformDepthImgToColorSensorEnabled</span>

**函数原型：**
VzReturnStatus 		VZ_SetTransformDepthImgToColorSensorEnabled(VzDeviceHandle device, 	bool bEnabled)
**函数功能：**
设置深度图像对齐到彩色相机空间的开关，只有带彩色传感器的设备才支持此操作。如果打开开关，则调用VZ_GetFrameReady时，VzFrameReady.transformedDepth的值为1，然后调用VZ_GetFrame可以得到VzTransformDepthImgToColorSensorFrame类型的深度图像，其大小与彩色图像大小相同。
**函数参数：**
VzDeviceHandle device： 设备句柄
bool bEnabled：true打开对齐，false关闭对齐
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.46  <span id="VZ_GetTransformDepthImgToColorSensorEnabled">VZ_GetTransformDepthImgToColorSensorEnabled</span>

**函数原型：**
VzReturnStatus 		VZ_GetTransformDepthImgToColorSensorEnabled(VzDeviceHandle device, 	bool *bEnabled)
**函数功能：**
获取深度图像对齐到彩色相机空间的开关状态
**函数参数：**
VzDeviceHandle device： 设备句柄
bool *bEnabled：返回开关状态
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.47  <span id="VZ_TransformedDepthPointToColorPoint">VZ_TransformedDepthPointToColorPoint</span>

**函数原型：**
VzReturnStatus VZ_TransformedDepthPointToColorPoint(const 	VzDeviceHandle device, const VzDepthVector3 depthPoint, const 	VzVector2u16 	colorSize, VzVector2u16* pPointInColor)
**函数功能：**
对齐深度图像上的点到彩色图像空间，可以在彩色图像上获得与传入的深度图像坐标点相对应的点的坐标
**函数参数：**
VzDeviceHandle device： 设备句柄
const VzDepthVector3 depthPoint：深度图像的坐标点
const VzVector2u16 colorSize：彩色图像尺寸
VzVector2u16* pPointInColor：获得的与深度图像的坐标点对应的彩色图像坐标点
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.48  <span id="VZ_ConvertDepthToPointCloud">VZ_ConvertDepthToPointCloud</span>

**函数原型：**
VzReturnStatus VZ_ConvertDepthToPointCloud(VzDeviceHandle device, 	VzDepthVector3* pDepthVector, VzVector3f* pWorldVector, int32_t 	pointCount, 	VzSensorIntrinsicParameters* pSensorParam)
**函数功能：**
把传入的深度图像坐标点集合转换为世界坐标系点集合。世界坐标原点在深度传感器镜头中心，Z轴垂直与设备前盖板，其正方向从设备指向远方；X轴从深度镜头指向激光器，其正方向从设备指向远方；Y轴垂直与设备指向地面，其正方向从设备指向远方。
**函数参数：**
VzDeviceHandle device： 设备句柄
VzDepthVector3* pDepthVector：深度图像的坐标点的集合
VzVector3f* pWorldVector：转换后点云的坐标点的集合
int32_t pointCount：坐标点的数目
VzSensorIntrinsicParameters* pSensorParam：传感器内参
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.49  <span id="VZ_ConvertDepthFrameToPointCloudVector">VZ_ConvertDepthFrameToPointCloudVector</span>

**函数原型：**
VzReturnStatus 	VZ_ConvertDepthFrameToPointCloudVector(VzDeviceHandle 	device, 	const VzFrame* pDepthFrame, VzVector3f* pWorldVector)
**函数功能：**
把传入的深度图像转换为世界坐标系点集合，转换后的世界坐标系点集合的大小为VzFrame.width * VzFrame.height，支持VzDepthFrame和VzTransformDepthImgToColorSensorFrame图像
**函数参数：**
VzDeviceHandle device： 设备句柄
const VzFrame* pDepthFrame：深度图像
VzVector3f* pWorldVector：转换后点云的坐标点的集合
**返回值:**
VzRetOK：调用成功
其他值：调用失败

### 3.50  <span id="VZ_SetHotPlugStatusCallback">VZ_SetHotPlugStatusCallback</span>

**函数原型：**
VzReturnStatus VZ_SetHotPlugStatusCallback(PtrHotPlugStatusCallback 	pCallback, const void* pUserData)
**函数功能：**
设置设备热拔插状态回调函数
**函数参数：**
PtrHotPlugStatusCallback pCallback： 回调函数
const void* pUserData：用户数据，可以为空
**返回值:**
VzRetOK：调用成功
其他值：调用失败

# demo示例

## 1 DevHotPlugCallbackC

示例简介：热插拔回调函数的设置及调用方法示例。

所涉及接口：

| [ VZ_Initialize](#VZ_Initialize)                            |
| ----------------------------------------------------------- |
| [VZ_GetDeviceCount](#VZ_GetDeviceCount)                     |
| [VZ_GetDeviceInfoList](VZ_GetDeviceInfoList)                |
| [VZ_OpenDeviceByUri](#VZ_OpenDeviceByUri)                   |
| [VZ_StartStream](#VZ_StartStream)                           |
| [VZ_SetHotPlugStatusCallback](#VZ_SetHotPlugStatusCallback) |
| [VZ_StopStream](#VZ_StopStream)                             |
| [VZ_CloseDevice](#VZ_CloseDevice)                           |
| [VZ_Shutdown](#VZ_Shutdown)                                 |

[ VZ_Initialize](#VZ_Initialize)

[VZ_Shutdown](#VZ_Shutdown)

Windows C++ 源代码：

```C++
#include <iostream>
#include <fstream>
#include "VzenseNebula_api.h"
#include <thread>

using namespace std;
VzDeviceInfo* pDeviceListInfo = NULL;
VzDeviceHandle deviceHandle = 0;


bool InitDevice(const int deviceCount);
void HotPlugStateCallback(const VzDeviceInfo *pInfo, int status, void *contex);

int main(int argc, char *argv[])
{
	uint32_t deviceCount = 0;

	VzReturnStatus status = VZ_Initialize();
	if (status != VzReturnStatus::VzRetOK)
	{
		cout << "VzInitialize failed status:" <<status << endl;
		system("pause");
		return -1;
	}

GET:
	status = VZ_GetDeviceCount(&deviceCount);
	if (status != VzReturnStatus::VzRetOK)
	{
		cout << "VzGetDeviceCount failed status:" <<status << endl;
		system("pause");
		return -1;
	}
	cout << "Get device count: " << deviceCount << endl;
	if (0 == deviceCount)
	{
		this_thread::sleep_for(chrono::seconds(1));
		goto GET;
	}

	if (InitDevice(deviceCount))
	{
		status = VZ_SetHotPlugStatusCallback(HotPlugStateCallback, nullptr);;
		if (status != VzReturnStatus::VzRetOK)
		{
			cout << "SetHotPlugStatusCallback failed status:" <<status << endl;
 		}
		else
		{
			cout <<" wait for hotplug operation "<<endl;
			// wait for hotplug
			for (;;)
			{	
				this_thread::sleep_for(chrono::seconds(1));
			}
		}
		status = VZ_CloseDevice(&deviceHandle);
		if (status != VzReturnStatus::VzRetOK)
		{
			cout << "CloseDevice failed status:" <<status << endl;
		}
	}
	status = VZ_Shutdown();  
	if (status != VzReturnStatus::VzRetOK)
	{
		cout << "Shutdown failed status:" <<status << endl;
	} 
 
	delete[] pDeviceListInfo;
	pDeviceListInfo = NULL;

	return 0;
}

bool InitDevice(const int deviceCount)
{
	if (pDeviceListInfo)
	{
		delete[] pDeviceListInfo;
		pDeviceListInfo = NULL;

	}

	pDeviceListInfo = new VzDeviceInfo[deviceCount];
	VzReturnStatus status = VZ_GetDeviceInfoList(deviceCount, pDeviceListInfo);
	if (status != VzReturnStatus::VzRetOK)
	{
		cout << "GetDeviceListInfo failed status:" << status << endl;
		return false;
	}
	else
	{
		if (VzConnected != pDeviceListInfo[0].status)
		{
			cout << "connect statu" << pDeviceListInfo[0].status << endl;
			cout << "Call VZ_OpenDevice with connect status :" << VzConnected << endl;
			return false;
		}
	}
	
	cout << "uri:" << pDeviceListInfo[0].uri << endl
	<< "alias:" << pDeviceListInfo[0].alias << endl
	<< "ip:" << pDeviceListInfo[0].ip << endl
	<< "connectStatus:" << pDeviceListInfo[0].status << endl;

	deviceHandle = 0;

	status = VZ_OpenDeviceByUri(pDeviceListInfo[0].uri, &deviceHandle);

	if (status != VzReturnStatus::VzRetOK)
	{
		cout << "OpenDevice failed status:" <<status << endl;
		return false;
	}

    cout << "open device successful,status :" << status << endl;

	status = VZ_StartStream(deviceHandle);

	if (status != VzReturnStatus::VzRetOK)
	{
		cout << "StartStream failed status:" <<status << endl;
		return false;
	}

	return true;
}

void HotPlugStateCallback(const VzDeviceInfo *pInfo, int status, void *contex)
{
	cout << "uri " << status << "  " << pInfo->uri << "    " << (status == 0 ? "add" : "remove") << endl;
	cout << "alias " << status << "  " << pInfo->alias << "    " << (status == 0 ? "add" : "remove") << endl;

	if (status == 0)
	{
		cout << "VZ_OpenDevice " << VZ_OpenDeviceByUri(pInfo->uri, &deviceHandle) << endl;
		cout << "VZ_StartStream " << VZ_StartStream(deviceHandle) << endl;
	}
	else
	{
		cout << "VZ_StopStream " << VZ_StopStream(deviceHandle) << endl;
		cout << "VZ_CloseDevice " << VZ_CloseDevice(&deviceHandle) << endl;
	}
}

```

python  源代码：

```python
from pickle import FALSE, TRUE
import sys
sys.path.append('../../../')

from API.VzenseDS_api import *
import time

camera = VzenseTofCam()


def HotPlugStateCallback(type_struct,  state = c_int32(0)):
    global camera
    if state ==0:
        print(str(type_struct.contents.alias) + "   add")
        ret = camera.VZ_OpenDeviceByUri(type_struct.contents.uri)
        if  ret == 0:
            print(str(type_struct.contents.alias) + " open success")
        else:
            print(str(type_struct.contents.alias) + " open failed",ret)
        ret = camera.VZ_StartStream()
        if  ret == 0:
            print(str(type_struct.contents.alias) + " startstream success")
        else:
            print(str(type_struct.contents.alias) + " startstream failed",ret)
    else:
        print(str(type_struct.contents.alias) + "   remove")
        ret = camera.VZ_StopStream()
        if  ret == 0:
            print(str(type_struct.contents.alias) + " stopstream success")
        else:
            print(str(type_struct.contents.alias) + " stopstream failed",ret)
        ret = camera.VZ_CloseDevice()
        if  ret == 0:
            print(str(type_struct.contents.alias) + " close success")
        else:
            print(str(type_struct.contents.alias) + " close failed",ret)

camera.VZ_SetHotPlugStatusCallback(HotPlugStateCallback)

camera_count = camera.VZ_GetDeviceCount()
retry_count = 100
while camera_count==0 and retry_count > 0:
    retry_count = retry_count-1
    camera_count = camera.VZ_GetDeviceCount()
    time.sleep(1)
    print("scaning......   ",retry_count)

device_info=VzDeviceInfo()

if camera_count > 1:
    ret,device_infolist=camera.VZ_GetDeviceInfoList(camera_count)
    if ret==0:
        device_info = device_infolist[0]
        for info in device_infolist: 
            print('cam uri:  ' + str(info.uri))
    else:
        print(' failed:' + ret)  
        exit()  
elif camera_count == 1:
    ret,device_info=camera.VZ_GetDeviceInfo()
    if ret==0:
        print('cam uri:' + str(device_info.uri))
    else:
        print(' failed:' + ret)   
        exit() 
else: 
    print("there are no camera found")
    exit()

print("uri: "+str(device_info.uri))
ret = camera.VZ_OpenDeviceByUri(device_info.uri)

if  ret == 0 or ret == -103:
    ret = camera.VZ_StartStream()
    if  ret == 0:
        print("startstream success")
    else:
        print("startstream failed",ret)

    while 1:
        ret, frameready = camera.VZ_GetFrameReady(c_uint16(1000))
        if  ret !=0:
            print("VZ_GetFrameReady failed:",ret)
            continue
  
        if  frameready.depth:      
            ret,frame = camera.VZ_GetFrame(VzFrameType.VzDepthFrame)
            if  ret ==0:
                print("frameIndex: ",frame.frameIndex)
            else:
                print("get depth frame failed ",ret)
            continue
else:
    print('VZ_OpenDeviceByUri failed: ' + str(ret))  

ret = camera.VZ_StopStream()
if  ret == 0:
    print("stopstream success")
else:
    print("stopstream failed",ret)

ret = camera.VZ_CloseDevice()     
if  ret == 0:
    print("close device successful")
else:
    print('VZ_CloseDevice failed: ' + str(ret))                         

```

