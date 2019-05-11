---
title: HTTP アダプターの構成およびチューニング パラメータ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, parameters
- configuring [HTTP adapters], parameters
- HTTP adapters, tuning
- RequestQueueSize key [HTTP adapters]
- HttpReceiveThreadsPerCpu key [HTTP adapters]
- HttpOutTimeoutInterval key [HTTP adapters]
- HttpOutInflightSize key [HTTP adapters]
- configuring [HTTP adapters], tuning
- DisableChunkEncoding key [HTTP adapters]
- HttpOutCompleteSize key [HTTP adapters]
ms.assetid: c8989a88-722a-40b5-94cf-4b6840add02e
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaae6d5cf3a5f810a8c8340a07d1a94fab974afe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383029"
---
# <a name="http-adapter-configuration-and-tuning-parameters"></a><span data-ttu-id="4a85a-102">HTTP アダプターの構成およびチューニング パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a85a-102">HTTP Adapter Configuration and Tuning Parameters</span></span>
<span data-ttu-id="4a85a-103">いくつかの構成およびチューニング パラメータは、HTTP アダプタと BizTalk Server のインストール ディレクトリのルートにある BTSNTSvc.exe.config ファイルの変更を使用してレジストリ キー エントリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4a85a-103">Several configuration and tuning parameters are accessible for the HTTP adapter through registry key entries and through the modification of the BTSNTSvc.exe.config file that is located in the root BizTalk Server installation directory.</span></span>  
  
 <span data-ttu-id="4a85a-104">**HTTP アダプターのパフォーマンスに影響を与えるレジストリ設定**</span><span class="sxs-lookup"><span data-stu-id="4a85a-104">**Registry Settings That Affect HTTP Adapter Performance**</span></span>  
  
 <span data-ttu-id="4a85a-105">次の表では、HTTP アダプタのパフォーマンスに影響するレジストリ設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a85a-105">The following table describes the registry settings that affect the performance of the HTTP adapter.</span></span> <span data-ttu-id="4a85a-106">既定でがない HTTP アダプタのキー レジストリでは、HTTP アダプター、既定の設定を使用するように注意してください。</span><span class="sxs-lookup"><span data-stu-id="4a85a-106">Note that by default there are no HTTP adapter keys in the registry, so the HTTP adapter uses the default settings.</span></span> <span data-ttu-id="4a85a-107">を既定の設定を変更する必要がある場合は、レジストリで、次の場所では、次のレジストリ キーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a85a-107">If it is necessary to change the default settings, you need to create the following registry keys under the following locations in the registry:</span></span>  
  
-   <span data-ttu-id="4a85a-108">**DisableChunkEncoding**、 **RequestQueueSize**、および**HttpReceiveThreadsPerCpu**で定義する必要があります**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\HttpReceive**します。</span><span class="sxs-lookup"><span data-stu-id="4a85a-108">**DisableChunkEncoding**, **RequestQueueSize**, and **HttpReceiveThreadsPerCpu** must be defined in **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\HttpReceive**.</span></span>  
  
-   <span data-ttu-id="4a85a-109">**HttpOutTimeoutInterval**、 **HttpOutInflightSize**、および**HttpOutCompleteSize**で定義する必要があります**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc {GUID}** 場所**GUID** HTTP 送信ハンドラのホストの ID です。</span><span class="sxs-lookup"><span data-stu-id="4a85a-109">**HttpOutTimeoutInterval**, **HttpOutInflightSize**, and **HttpOutCompleteSize** must be defined in **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{GUID}** where **GUID** is the ID of the host for the HTTP send handler.</span></span>  
  
|<span data-ttu-id="4a85a-110">キー名</span><span class="sxs-lookup"><span data-stu-id="4a85a-110">Key name</span></span>|<span data-ttu-id="4a85a-111">型</span><span class="sxs-lookup"><span data-stu-id="4a85a-111">Type</span></span>|<span data-ttu-id="4a85a-112">既定</span><span class="sxs-lookup"><span data-stu-id="4a85a-112">Default</span></span>|<span data-ttu-id="4a85a-113">説明</span><span class="sxs-lookup"><span data-stu-id="4a85a-113">Explanation</span></span>|  
|--------------|----------|-------------|-----------------|  
|<span data-ttu-id="4a85a-114">**DisableChunkEncoding**</span><span class="sxs-lookup"><span data-stu-id="4a85a-114">**DisableChunkEncoding**</span></span>|<span data-ttu-id="4a85a-115">DWORD</span><span class="sxs-lookup"><span data-stu-id="4a85a-115">DWORD</span></span>|<span data-ttu-id="4a85a-116">0</span><span class="sxs-lookup"><span data-stu-id="4a85a-116">0</span></span>|<span data-ttu-id="4a85a-117">規制アダプターが、クライアントへの応答を送信するときに、チャンク エンコードを使用して、HTTP 受信かどうか。</span><span class="sxs-lookup"><span data-stu-id="4a85a-117">Regulates whether or not the HTTP receive adapter uses chunked encoding when sending responses back to the client.</span></span><br /><br /> <span data-ttu-id="4a85a-118">HTTP 受信アダプタの応答にチャンク エンコードをオフに 0 以外の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="4a85a-118">Set to a nonzero value to turn off chunked encoding for HTTP receive adapter responses.</span></span><br /><br /> <span data-ttu-id="4a85a-119">**最小値:** 0</span><span class="sxs-lookup"><span data-stu-id="4a85a-119">**Minimum value:** 0</span></span><br /><br /> <span data-ttu-id="4a85a-120">**最大値:** 0 以外の値</span><span class="sxs-lookup"><span data-stu-id="4a85a-120">**Maximum value:** Any nonzero value</span></span>|  
|<span data-ttu-id="4a85a-121">**RequestQueueSize**</span><span class="sxs-lookup"><span data-stu-id="4a85a-121">**RequestQueueSize**</span></span>|<span data-ttu-id="4a85a-122">DWORD</span><span class="sxs-lookup"><span data-stu-id="4a85a-122">DWORD</span></span>|<span data-ttu-id="4a85a-123">256</span><span class="sxs-lookup"><span data-stu-id="4a85a-123">256</span></span>|<span data-ttu-id="4a85a-124">受信アダプターの処理を同時に、HTTP の同時要求の数を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a85a-124">Defines the number of concurrent requests that the HTTP receive adapter processes at one time.</span></span><br /><br /> <span data-ttu-id="4a85a-125">**最小値:** 10</span><span class="sxs-lookup"><span data-stu-id="4a85a-125">**Minimum value:**  10</span></span><br /><br /> <span data-ttu-id="4a85a-126">**最大値:** 2048</span><span class="sxs-lookup"><span data-stu-id="4a85a-126">**Maximum value:** 2048</span></span>|  
|<span data-ttu-id="4a85a-127">**HttpReceiveThreadsPerCpu**</span><span class="sxs-lookup"><span data-stu-id="4a85a-127">**HttpReceiveThreadsPerCpu**</span></span>|<span data-ttu-id="4a85a-128">DWORD</span><span class="sxs-lookup"><span data-stu-id="4a85a-128">DWORD</span></span>|<span data-ttu-id="4a85a-129">2</span><span class="sxs-lookup"><span data-stu-id="4a85a-129">2</span></span>|<span data-ttu-id="4a85a-130">定義受信アダプター、HTTP に割り当てられている CPU あたりのスレッドの数。</span><span class="sxs-lookup"><span data-stu-id="4a85a-130">Defines the number of threads per CPU that are allocated to the HTTP receive adapter.</span></span><br /><br /> <span data-ttu-id="4a85a-131">**最小値:** 1</span><span class="sxs-lookup"><span data-stu-id="4a85a-131">**Minimum value:** 1</span></span><br /><br /> <span data-ttu-id="4a85a-132">**最大値:** 10</span><span class="sxs-lookup"><span data-stu-id="4a85a-132">**Maximum value:** 10</span></span>|  
|<span data-ttu-id="4a85a-133">**HttpOutTimeoutInterval**</span><span class="sxs-lookup"><span data-stu-id="4a85a-133">**HttpOutTimeoutInterval**</span></span>|<span data-ttu-id="4a85a-134">DWORD</span><span class="sxs-lookup"><span data-stu-id="4a85a-134">DWORD</span></span>|<span data-ttu-id="4a85a-135">2000</span><span class="sxs-lookup"><span data-stu-id="4a85a-135">2000</span></span>|<span data-ttu-id="4a85a-136">HTTP 送信アダプターがタイムアウトになるまで待機する秒単位で間隔を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a85a-136">Defines the interval in seconds that the HTTP send adapter will wait before timing out.</span></span><br /><br /> <span data-ttu-id="4a85a-137">**最小値:** 500</span><span class="sxs-lookup"><span data-stu-id="4a85a-137">**Minimum value:** 500</span></span><br /><br /> <span data-ttu-id="4a85a-138">**最大値:** 10000000</span><span class="sxs-lookup"><span data-stu-id="4a85a-138">**Maximum value:** 10000000</span></span>|  
|<span data-ttu-id="4a85a-139">**HttpOutInflightSize**</span><span class="sxs-lookup"><span data-stu-id="4a85a-139">**HttpOutInflightSize**</span></span>|<span data-ttu-id="4a85a-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="4a85a-140">DWORD</span></span>|<span data-ttu-id="4a85a-141">100</span><span class="sxs-lookup"><span data-stu-id="4a85a-141">100</span></span>|<span data-ttu-id="4a85a-142">これは、BizTalk Server の HTTP 送信アダプタのインスタンスを処理する同時実行の HTTP 要求の最大数です。</span><span class="sxs-lookup"><span data-stu-id="4a85a-142">This is the maximum number of concurrent HTTP requests that BizTalk Server HTTP send adapter instance will handle.</span></span><br /><br /> <span data-ttu-id="4a85a-143">待機時間の推奨値が 3 ~ 5 倍の間は、 **maxconnection**構成ファイルのエントリ以下で説明します。</span><span class="sxs-lookup"><span data-stu-id="4a85a-143">The recommended value for latency is between 3 to 5 times that of the **maxconnection** configuration file entry discussed below.</span></span><br /><br /> <span data-ttu-id="4a85a-144">**最小値:** 1</span><span class="sxs-lookup"><span data-stu-id="4a85a-144">**Minimum value:** 1</span></span><br /><br /> <span data-ttu-id="4a85a-145">**最大値:** 1024</span><span class="sxs-lookup"><span data-stu-id="4a85a-145">**Maximum value:** 1024</span></span>|  
|<span data-ttu-id="4a85a-146">**HttpOutCompleteSize**</span><span class="sxs-lookup"><span data-stu-id="4a85a-146">**HttpOutCompleteSize**</span></span>|<span data-ttu-id="4a85a-147">DWORD</span><span class="sxs-lookup"><span data-stu-id="4a85a-147">DWORD</span></span>|<span data-ttu-id="4a85a-148">5</span><span class="sxs-lookup"><span data-stu-id="4a85a-148">5</span></span>|<span data-ttu-id="4a85a-149">コントロールの HTTP から返されるメッセージのバッチ サイズは、アダプターを送信します。</span><span class="sxs-lookup"><span data-stu-id="4a85a-149">Controls the size of the batch of messages that is returned from the HTTP send adapter.</span></span> <span data-ttu-id="4a85a-150">バッファーがいっぱいでないと、未処理の応答がある場合、アダプターは、バッチがコミットされるまで 1 秒間待機します。</span><span class="sxs-lookup"><span data-stu-id="4a85a-150">If the buffer is not full and there are outstanding responses then the adapter will wait for 1 second until it commits the batch.</span></span>  <span data-ttu-id="4a85a-151">低待機時間シナリオは、これは処理のメッセージ ボックスにすぐに応答メッセージを送信するアダプターを 1 に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a85a-151">For low-latency scenarios this should be set to 1 which will allow the adapter to send response messages immediately to the message box for processing.</span></span><br /><br /> <span data-ttu-id="4a85a-152">**最小値:** 1</span><span class="sxs-lookup"><span data-stu-id="4a85a-152">**Minimum value:** 1</span></span><br /><br /> <span data-ttu-id="4a85a-153">**最大値:** 1024</span><span class="sxs-lookup"><span data-stu-id="4a85a-153">**Maximum value:** 1024</span></span>|  
  
 <span data-ttu-id="4a85a-154">**特定の宛先サーバーに HTTP 送信アダプターによって行われる同時接続数を制御する構成ファイル エントリ**</span><span class="sxs-lookup"><span data-stu-id="4a85a-154">**Configuration File Entry to Govern the Number of Concurrent Connections Made by the HTTP Send Adapter to a Particular Destination Server**</span></span>  
  
 <span data-ttu-id="4a85a-155">HTTP アダプターが、特定の移行先サーバーに表示される同時接続数は、BizTalk Server のインストール ディレクトリのルートにある BTSNTSvc.exe.config ファイルにエントリを作成して構成できます。</span><span class="sxs-lookup"><span data-stu-id="4a85a-155">The number of concurrent connections that the HTTP adapter opens for a particular destination server can be configured by making an entry in the BTSNTSvc.exe.config file that is located in the root BizTalk Server installation directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a85a-156">このプロパティから同じ HTTP サーバーにメッセージを送信する場合、HTTP および SOAP の両方のアダプターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4a85a-156">This property will be applied to both HTTP and SOAP adapters if they send messages to the same destination HTTP server.</span></span> <span data-ttu-id="4a85a-157">"Maxconnnection"プロパティの既定値は 2、すべての Uri の"maxconnection"プロパティを設定できる最大値は 20 です。</span><span class="sxs-lookup"><span data-stu-id="4a85a-157">The default value for the “maxconnnection” property is 2, the maximum value that can be set for the “maxconnection” property for all URIs is 20.</span></span>  
  
 <span data-ttu-id="4a85a-158">"最大接続数" プロパティの構成例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4a85a-158">The following is an example of the configuration for the maximum connections property:</span></span>  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "20" />  
      <add address = "http://www.northwind.com" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a85a-159">参照</span><span class="sxs-lookup"><span data-stu-id="4a85a-159">See Also</span></span>  
 [<span data-ttu-id="4a85a-160">HTTP アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="4a85a-160">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)