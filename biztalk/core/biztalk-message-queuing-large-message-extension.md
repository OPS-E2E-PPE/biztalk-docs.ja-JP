---
title: BizTalk メッセージ キューの大きいメッセージ用拡張機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Message Queuing Large Message Extension
- utilities, BizTalk Message Queuing Large Message Extension
ms.assetid: 5d6892d3-fda8-41a3-8111-d28c11bd71fb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb50b2e3270644a73dd3fb4f3b11af4da2dc0f72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020512"
---
# <a name="biztalk-message-queuing-large-message-extension"></a><span data-ttu-id="48606-102">BizTalk メッセージ キューのサイズの大きいメッセージ用拡張機能</span><span class="sxs-lookup"><span data-stu-id="48606-102">BizTalk Message Queuing Large Message Extension</span></span>
<span data-ttu-id="48606-103">4megabytes よりも大きい本文と共にメッセージを処理できないネイティブのメッセージ キュー (MB)。</span><span class="sxs-lookup"><span data-stu-id="48606-103">Native message queuing cannot process a message with a body larger than 4megabytes (MB).</span></span> <span data-ttu-id="48606-104">ただし、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、4 MB を超えるメッセージを処理できるようにする、ネイティブのメッセージ キュー用のアドオンが用意されています。</span><span class="sxs-lookup"><span data-stu-id="48606-104">However, Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes an add-on for native message queuing that permits processing messages larger than 4 MB.</span></span> <span data-ttu-id="48606-105">このアドオンは、Mqrtlarge.dll ファイルとして配信し、公開、 **MQSendLargeMessage**と**MQReceiveLargeMessage**アプリケーション プログラミング インターフェイス (Api)、および COM 類似モデル。</span><span class="sxs-lookup"><span data-stu-id="48606-105">This add-on is delivered as the Mqrtlarge.dll file, and exposes the **MQSendLargeMessage** and **MQReceiveLargeMessage** application programming interfaces (APIs), and the analogous COM model.</span></span> <span data-ttu-id="48606-106">これらの関数は、標準メッセージ キュー Api として実装されます**MQSendMessage**と**MQReceiveMessage**それぞれします。</span><span class="sxs-lookup"><span data-stu-id="48606-106">These functions are implemented as standard message queuing APIs, **MQSendMessage** and **MQReceiveMessage** respectively.</span></span>  

 <span data-ttu-id="48606-107">サイズの大きいメッセージの交換に参加するには、メッセージ キュー コンピューターに Mqrtlarge.dll ファイルをインストールし、メッセージ キュー アプリケーションでアドオン API を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48606-107">To participate in large message exchanges, the message queuing computer must have the Mqrtlarge.dll file installed, and the message queuing application should use the add-on APIs.</span></span> <span data-ttu-id="48606-108">それ以外の場合、完全なメッセージをフラグメント化されます。</span><span class="sxs-lookup"><span data-stu-id="48606-108">Otherwise, complete messages will be fragmented.</span></span>  

 <span data-ttu-id="48606-109">**SDK の場所**</span><span class="sxs-lookup"><span data-stu-id="48606-109">**Location in SDK**</span></span>  

 <span data-ttu-id="48606-110">\<*インストール パス*\>\SDK\ Mqrtlarge.dll</span><span class="sxs-lookup"><span data-stu-id="48606-110">\<*Installation Path*\>\SDK\ Mqrtlarge.dll</span></span>  

 <span data-ttu-id="48606-111">**ファイルのインベントリ**</span><span class="sxs-lookup"><span data-stu-id="48606-111">**File Inventory**</span></span>  

 <span data-ttu-id="48606-112">次の表は、このユーティリティで使用するファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="48606-112">The following table shows the file this utility uses and describes its purpose.</span></span>  


|    <span data-ttu-id="48606-113">ファイル</span><span class="sxs-lookup"><span data-stu-id="48606-113">File(s)</span></span>    |                                                                                                                                                                                              <span data-ttu-id="48606-114">説明</span><span class="sxs-lookup"><span data-stu-id="48606-114">Description</span></span>                                                                                                                                                                                               |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="48606-115">Mqrtlarge.dll</span><span class="sxs-lookup"><span data-stu-id="48606-115">Mqrtlarge.dll</span></span> | <span data-ttu-id="48606-116">公開する Win32 ダイナミック リンク ライブラリ**MQSendLargeMessage**と**MQReceiveLargeMessage**します。</span><span class="sxs-lookup"><span data-stu-id="48606-116">A Win32 dynamic-link library that exposes **MQSendLargeMessage** and **MQReceiveLargeMessage**.</span></span><br /><br /> <span data-ttu-id="48606-117">ヘッダー ファイルにある、 *\<インストール パス\>* \SDK\Include ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="48606-117">The header files are located in the *\<Installation Path\>* \SDK\Include directory.</span></span> <span data-ttu-id="48606-118">**注:** インストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を 64 ビット版の Mqrtlarge.dll にアクセスするために Windows の 64 ビット バージョン。</span><span class="sxs-lookup"><span data-stu-id="48606-118">**Note:**  You must install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] onto a 64 bit version of Windows in order to access the 64 bit version of Mqrtlarge.dll.</span></span> |

 <span data-ttu-id="48606-119">**このユーティリティの使用**</span><span class="sxs-lookup"><span data-stu-id="48606-119">**Using This Utility**</span></span>  

 <span data-ttu-id="48606-120">Mqrtlarge.dll ファイルを実行するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="48606-120">Use the following procedure to run the Mqrtlarge.dll file.</span></span>  

### <a name="to-use-the-mqrtlargedll-file"></a><span data-ttu-id="48606-121">Mqrtlarge.dll ファイルを使用するには</span><span class="sxs-lookup"><span data-stu-id="48606-121">To use the Mqrtlarge.dll file</span></span>  

1. > [!NOTE]
   >  <span data-ttu-id="48606-122">BizTalk Server なしの MSMQ ソリューションでは、可能性があります、まだ、MQRTLarge.dll から正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="48606-122">For an MSMQ solution without BizTalk Server, the MQRTLarge.dll may still function correctly.</span></span> <span data-ttu-id="48606-123">ただし、これは Microsoft がサポートしている推奨構成ではありませんし、BizTalk Server 環境の外部で使用されている場合に、予期しない結果が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="48606-123">However, this is not a recommended configuration that Microsoft supports, and unexpected results may occur if used outside of the BizTalk Server environment.</span></span>  

    <span data-ttu-id="48606-124">ファイル Mqrtlarge.dll を BizTalk Server がインストールされていないコンピューターに追加します。</span><span class="sxs-lookup"><span data-stu-id="48606-124">Add the file Mqrtlarge.dll to the computer that does not contain an installation of BizTalk Server.</span></span> <span data-ttu-id="48606-125">メッセージ キューで Mqrtlarge.dll を使用して、BizTalk Server との間でメッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="48606-125">Message Queuing uses Mqrtlarge.dll to send or receive messages to or from BizTalk Server.</span></span>  

2. <span data-ttu-id="48606-126">Mqrtlarge.dll ファイルの API にアクセスするには、他のコンピューターへのメッセージの送信や他のコンピューターから BizTalk メッセージ キューのエンドポイントへのメッセージの受信を行うアプリケーションに、Mqrtlarge.dll ファイルへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="48606-126">To access the APIs in the Mqrtlarge.dll file, add a reference to the Mqrtlarge.dll file in the applications that send or receive messages to or from other computers to the BizTalk Message Queuing endpoint.</span></span>  

   <span data-ttu-id="48606-127">**解説**</span><span class="sxs-lookup"><span data-stu-id="48606-127">**Remarks**</span></span>  

   <span data-ttu-id="48606-128">サイズの大きいメッセージは、標準メッセージ キュー (MSMQ とも呼ばれます) のキューに送信されます。</span><span class="sxs-lookup"><span data-stu-id="48606-128">Large messages are sent to standard Message Queuing (also known as MSMQ) queues.</span></span> <span data-ttu-id="48606-129">サイズの大きいメッセージ API はこれらのキューでのみ使用することをお勧めしますが、強制されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="48606-129">You should use only the large message APIs on such queues, although this is not enforced.</span></span>  

   <span data-ttu-id="48606-130">使用することもできます**MQSendMessage**サイズの大きいメッセージを送信したキューにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="48606-130">You can still use **MQSendMessage** to send messages to a queue to which you sent large messages.</span></span> <span data-ttu-id="48606-131">同様に、使用**MQReceiveMessage**のパフォーマンスに影響を与える可能性があるためにお勧めしませんが、これらのキューからメッセージを受信する、 **MQReceiveLargeMessage** API。</span><span class="sxs-lookup"><span data-stu-id="48606-131">Likewise, you can use **MQReceiveMessage** to receive messages from such queues, although it is not recommended because it may impact the performance of the **MQReceiveLargeMessage** API.</span></span>  

   <span data-ttu-id="48606-132">回復のために、お勧めを使用すること**DEAD_LETTER**ジャーナリングです。</span><span class="sxs-lookup"><span data-stu-id="48606-132">For recovery purposes, it is recommended that you use **DEAD_LETTER** journaling.</span></span>  

   <span data-ttu-id="48606-133">**断片化**</span><span class="sxs-lookup"><span data-stu-id="48606-133">**Fragmentation**</span></span>  

   <span data-ttu-id="48606-134">一般に、それぞれ、4 MB より小さい多数のメッセージにサイズの大きいメッセージをフラグメント化されます。</span><span class="sxs-lookup"><span data-stu-id="48606-134">In general, a large message will be fragmented into numerous messages, each smaller than 4 MB.</span></span> <span data-ttu-id="48606-135">フラグメント化されるのは本文だけであることを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="48606-135">It is important to understand that only the body is fragmented.</span></span> <span data-ttu-id="48606-136">残りのプロパティは各フラグメントと共に送信されます。</span><span class="sxs-lookup"><span data-stu-id="48606-136">The rest of the properties are sent with each fragment.</span></span>  

   <span data-ttu-id="48606-137">フラグメントの数は、メッセージのサイズとフラグメントのサイズによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="48606-137">The number of fragments is defined by the size of the message and the size of the fragments.</span></span> <span data-ttu-id="48606-138">フラグメント サイズは、ファイル Mqrtlarge.dll または BizTalk メッセージ キューの適切な部分によって自動的に決まることもあります。</span><span class="sxs-lookup"><span data-stu-id="48606-138">The fragment size may be automatically determined by the file Mqrtlarge.dll or the appropriate part of BizTalk Message Queuing.</span></span> <span data-ttu-id="48606-139">アプリケーションでフラグメント サイズを明示的に指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="48606-139">Applications can also explicitly specify the fragment size.</span></span>  

   <span data-ttu-id="48606-140">サイズの大きいメッセージ用拡張機能では、一定サイズの追加内部データを追加することでメッセージを拡張する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="48606-140">Note that the large message extension requires extending the message by adding additional internal data of a constant size.</span></span>  

   <span data-ttu-id="48606-141">**PROPID_M_EXTENSION**</span><span class="sxs-lookup"><span data-stu-id="48606-141">**PROPID_M_EXTENSION**</span></span>  

   <span data-ttu-id="48606-142">使用することができます、 **PROPID_M_EXTENSION/PROPID_M_EXTENSION_LEN**プロパティをメッセージに署名します。</span><span class="sxs-lookup"><span data-stu-id="48606-142">You can use the **PROPID_M_EXTENSION/PROPID_M_EXTENSION_LEN** properties to sign the message.</span></span> <span data-ttu-id="48606-143">署名には、40 バイト (B) が構成されています。</span><span class="sxs-lookup"><span data-stu-id="48606-143">The signature comprises 40 bytes (B).</span></span> <span data-ttu-id="48606-144">次の表に、署名のフラグメントを示します。</span><span class="sxs-lookup"><span data-stu-id="48606-144">The following table shows signature fragments.</span></span>  

|<span data-ttu-id="48606-145">説明</span><span class="sxs-lookup"><span data-stu-id="48606-145">Description</span></span>|<span data-ttu-id="48606-146">サイズ</span><span class="sxs-lookup"><span data-stu-id="48606-146">Size</span></span>|  
|-----------------|----------|  
|<span data-ttu-id="48606-147">グローバル一意識別子 (GUID) を使用してこのメッセージが送信されたことを示す**MQSendLargeMessage**</span><span class="sxs-lookup"><span data-stu-id="48606-147">Globally unique identifier (GUID) denoting that this message was sent using **MQSendLargeMessage**</span></span>|<span data-ttu-id="48606-148">16 B</span><span class="sxs-lookup"><span data-stu-id="48606-148">16 B</span></span>|  
|<span data-ttu-id="48606-149">メッセージの GUID: メッセージのすべての部分に共通するあたりサイズの大きいメッセージの一意の ID</span><span class="sxs-lookup"><span data-stu-id="48606-149">GUID for the message: unique per-large message ID that is common to all parts of the message</span></span>|<span data-ttu-id="48606-150">16 B</span><span class="sxs-lookup"><span data-stu-id="48606-150">16 B</span></span>|  
|<span data-ttu-id="48606-151">サイズの大きいメッセージの合計サイズ</span><span class="sxs-lookup"><span data-stu-id="48606-151">Total size of the large message</span></span>|<span data-ttu-id="48606-152">4 B</span><span class="sxs-lookup"><span data-stu-id="48606-152">4 B</span></span>|  
|<span data-ttu-id="48606-153">部分番号</span><span class="sxs-lookup"><span data-stu-id="48606-153">Part number</span></span>|<span data-ttu-id="48606-154">2 B</span><span class="sxs-lookup"><span data-stu-id="48606-154">2 B</span></span>|  
|<span data-ttu-id="48606-155">メッセージ部分の数</span><span class="sxs-lookup"><span data-stu-id="48606-155">Number of message parts</span></span>|<span data-ttu-id="48606-156">2 B</span><span class="sxs-lookup"><span data-stu-id="48606-156">2 B</span></span>|  

 <span data-ttu-id="48606-157">使用するか**PROPID_M_EXTENSION**がその他の暗黙的です。</span><span class="sxs-lookup"><span data-stu-id="48606-157">The decision to use **PROPID_M_EXTENSION** has an additional implication.</span></span> <span data-ttu-id="48606-158">Microsoft Host Integration Server の MSMQ-MQSeries ブリッジでは、このプロパティを使用して、MQSeries とメッセージ キューのメッセージの間では直接マップされないプロパティを含む構造体を渡します。</span><span class="sxs-lookup"><span data-stu-id="48606-158">The Microsoft Host Integration Server MSMQ-MQSeries Bridge uses this property to pass a structure that contains properties that are not mapped directly between MQSeries and Message Queuing messages.</span></span> <span data-ttu-id="48606-159">メッセージを MQSeries に、または MQSeries から送信するアプリケーションは、この構造体を明示的または暗黙的に使用します。</span><span class="sxs-lookup"><span data-stu-id="48606-159">Applications that send messages to and from MQSeries explicitly or implicitly use this structure.</span></span> <span data-ttu-id="48606-160">メッセージが受信側アプリケーションでキューから受信されたとき、メッセージ キューでは受信確認を生成することができます。</span><span class="sxs-lookup"><span data-stu-id="48606-160">Message Queuing can generate acknowledgments when a message has been received from a queue by a receiving application.</span></span> <span data-ttu-id="48606-161">受信確認は、送信アプリケーションによって指定されたキューに送信されます。</span><span class="sxs-lookup"><span data-stu-id="48606-161">The acknowledgments are sent to a queue specified by the sending application.</span></span> <span data-ttu-id="48606-162">サイズの大きいメッセージの場合は、サイズの大きいメッセージの最後の部分についてのみこの受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="48606-162">In the case of large messages, you send this acknowledgment only for the last part of the large message.</span></span>  

## <a name="see-also"></a><span data-ttu-id="48606-163">参照</span><span class="sxs-lookup"><span data-stu-id="48606-163">See Also</span></span>  
 [<span data-ttu-id="48606-164">SDK のユーティリティ</span><span class="sxs-lookup"><span data-stu-id="48606-164">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)