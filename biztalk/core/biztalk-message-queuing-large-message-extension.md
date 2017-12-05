---
title: "BizTalk メッセージ キューの大きいメッセージ用拡張機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Message Queuing Large Message Extension
- utilities, BizTalk Message Queuing Large Message Extension
ms.assetid: 5d6892d3-fda8-41a3-8111-d28c11bd71fb
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 399c8e02d59a931dbf30bfa31ca28980dfa312be
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="biztalk-message-queuing-large-message-extension"></a><span data-ttu-id="b24db-102">BizTalk メッセージ キューのサイズの大きいメッセージ用拡張機能</span><span class="sxs-lookup"><span data-stu-id="b24db-102">BizTalk Message Queuing Large Message Extension</span></span>
<span data-ttu-id="b24db-103">4megabytes よりも大きい本体を持つメッセージを処理できないネイティブのメッセージ キュー (MB)。</span><span class="sxs-lookup"><span data-stu-id="b24db-103">Native message queuing cannot process a message with a body larger than 4megabytes (MB).</span></span> <span data-ttu-id="b24db-104">ただし、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、4 MB を超えるメッセージを処理できるようにする、ネイティブのメッセージ キュー用のアドオンが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b24db-104">However, Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes an add-on for native message queuing that permits processing messages larger than 4 MB.</span></span> <span data-ttu-id="b24db-105">このアドオンは、Mqrtlarge.dll ファイルとして提供され、公開、 **MQSendLargeMessage**と**MQReceiveLargeMessage**アプリケーション プログラミング インターフェイス (Api)、および COM 類似モデル。</span><span class="sxs-lookup"><span data-stu-id="b24db-105">This add-on is delivered as the Mqrtlarge.dll file, and exposes the **MQSendLargeMessage** and **MQReceiveLargeMessage** application programming interfaces (APIs), and the analogous COM model.</span></span> <span data-ttu-id="b24db-106">これらの関数は、標準メッセージ キュー Api として実装されて**MQSendMessage**と**MQReceiveMessage**それぞれします。</span><span class="sxs-lookup"><span data-stu-id="b24db-106">These functions are implemented as standard message queuing APIs, **MQSendMessage** and **MQReceiveMessage** respectively.</span></span>  
  
 <span data-ttu-id="b24db-107">サイズの大きいメッセージの交換に参加するには、メッセージ キュー コンピューターに Mqrtlarge.dll ファイルをインストールし、メッセージ キュー アプリケーションでアドオン API を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b24db-107">To participate in large message exchanges, the message queuing computer must have the Mqrtlarge.dll file installed, and the message queuing application should use the add-on APIs.</span></span> <span data-ttu-id="b24db-108">それ以外の場合、完全なメッセージをフラグメント化されます。</span><span class="sxs-lookup"><span data-stu-id="b24db-108">Otherwise, complete messages will be fragmented.</span></span>  
  
 <span data-ttu-id="b24db-109">**SDK 内の場所**</span><span class="sxs-lookup"><span data-stu-id="b24db-109">**Location in SDK**</span></span>  
  
 <span data-ttu-id="b24db-110">\<*インストール パス*\>\SDK\ Mqrtlarge.dll</span><span class="sxs-lookup"><span data-stu-id="b24db-110">\<*Installation Path*\>\SDK\ Mqrtlarge.dll</span></span>  
  
 <span data-ttu-id="b24db-111">**ファイルのインベントリ**</span><span class="sxs-lookup"><span data-stu-id="b24db-111">**File Inventory**</span></span>  
  
 <span data-ttu-id="b24db-112">次の表は、このユーティリティで使用するファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="b24db-112">The following table shows the file this utility uses and describes its purpose.</span></span>  
  
|<span data-ttu-id="b24db-113">ファイル</span><span class="sxs-lookup"><span data-stu-id="b24db-113">File(s)</span></span>|<span data-ttu-id="b24db-114">Description</span><span class="sxs-lookup"><span data-stu-id="b24db-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b24db-115">Mqrtlarge.dll</span><span class="sxs-lookup"><span data-stu-id="b24db-115">Mqrtlarge.dll</span></span>|<span data-ttu-id="b24db-116">公開する Win32 ダイナミック リンク ライブラリ**MQSendLargeMessage**と**MQReceiveLargeMessage**です。</span><span class="sxs-lookup"><span data-stu-id="b24db-116">A Win32 dynamic-link library that exposes **MQSendLargeMessage** and **MQReceiveLargeMessage**.</span></span><br /><br /> <span data-ttu-id="b24db-117">ヘッダー ファイルに配置されます、 *\<インストール パス\>*\SDK\Include ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="b24db-117">The header files are located in the *\<Installation Path\>*\SDK\Include directory.</span></span> <span data-ttu-id="b24db-118">**注:**インストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット版の Mqrtlarge.dll にアクセスするために Windows の 64 ビット バージョンにします。</span><span class="sxs-lookup"><span data-stu-id="b24db-118">**Note:**  You must install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] onto a 64 bit version of Windows in order to access the 64 bit version of Mqrtlarge.dll.</span></span>|  
  
 <span data-ttu-id="b24db-119">**このユーティリティの使用**</span><span class="sxs-lookup"><span data-stu-id="b24db-119">**Using This Utility**</span></span>  
  
 <span data-ttu-id="b24db-120">Mqrtlarge.dll ファイルを実行するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b24db-120">Use the following procedure to run the Mqrtlarge.dll file.</span></span>  
  
### <a name="to-use-the-mqrtlargedll-file"></a><span data-ttu-id="b24db-121">Mqrtlarge.dll ファイルを使用するには</span><span class="sxs-lookup"><span data-stu-id="b24db-121">To use the Mqrtlarge.dll file</span></span>  
  
1.  > [!NOTE]
    >  <span data-ttu-id="b24db-122">BizTalk Server なしの MSMQ ソリューションでは、引き続き、MQRTLarge.dll から正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="b24db-122">For an MSMQ solution without BizTalk Server, the MQRTLarge.dll may still function correctly.</span></span> <span data-ttu-id="b24db-123">ただし、これは Microsoft がサポートするための推奨構成ではありません、BizTalk Server 環境の外部で使用されている場合に、予期しない結果が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b24db-123">However, this is not a recommended configuration that Microsoft supports, and unexpected results may occur if used outside of the BizTalk Server environment.</span></span>  
  
     <span data-ttu-id="b24db-124">ファイル Mqrtlarge.dll を BizTalk Server がインストールされていないコンピューターに追加します。</span><span class="sxs-lookup"><span data-stu-id="b24db-124">Add the file Mqrtlarge.dll to the computer that does not contain an installation of BizTalk Server.</span></span> <span data-ttu-id="b24db-125">メッセージ キューで Mqrtlarge.dll を使用して、BizTalk Server との間でメッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="b24db-125">Message Queuing uses Mqrtlarge.dll to send or receive messages to or from BizTalk Server.</span></span>  
  
2.  <span data-ttu-id="b24db-126">Mqrtlarge.dll ファイルの API にアクセスするには、他のコンピューターへのメッセージの送信や他のコンピューターから BizTalk メッセージ キューのエンドポイントへのメッセージの受信を行うアプリケーションに、Mqrtlarge.dll ファイルへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="b24db-126">To access the APIs in the Mqrtlarge.dll file, add a reference to the Mqrtlarge.dll file in the applications that send or receive messages to or from other computers to the BizTalk Message Queuing endpoint.</span></span>  
  
 <span data-ttu-id="b24db-127">**「解説」**</span><span class="sxs-lookup"><span data-stu-id="b24db-127">**Remarks**</span></span>  
  
 <span data-ttu-id="b24db-128">サイズの大きいメッセージは、標準メッセージ キュー (MSMQ とも呼ばれます) のキューに送信されます。</span><span class="sxs-lookup"><span data-stu-id="b24db-128">Large messages are sent to standard Message Queuing (also known as MSMQ) queues.</span></span> <span data-ttu-id="b24db-129">サイズの大きいメッセージ API はこれらのキューでのみ使用することをお勧めしますが、強制されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="b24db-129">You should use only the large message APIs on such queues, although this is not enforced.</span></span>  
  
 <span data-ttu-id="b24db-130">使用することもできます**MQSendMessage**サイズの大きいメッセージを送信したキューにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="b24db-130">You can still use **MQSendMessage** to send messages to a queue to which you sent large messages.</span></span> <span data-ttu-id="b24db-131">同様に、使用することができます**MQReceiveMessage**のパフォーマンスに影響を与える可能性があるために推奨されませんが、このようなキューからメッセージを受信する、 **MQReceiveLargeMessage** API です。</span><span class="sxs-lookup"><span data-stu-id="b24db-131">Likewise, you can use **MQReceiveMessage** to receive messages from such queues, although it is not recommended because it may impact the performance of the **MQReceiveLargeMessage** API.</span></span>  
  
 <span data-ttu-id="b24db-132">回復用に、お勧めを使用すること**DEAD_LETTER**履歴。</span><span class="sxs-lookup"><span data-stu-id="b24db-132">For recovery purposes, it is recommended that you use **DEAD_LETTER** journaling.</span></span>  
  
 <span data-ttu-id="b24db-133">**断片化**</span><span class="sxs-lookup"><span data-stu-id="b24db-133">**Fragmentation**</span></span>  
  
 <span data-ttu-id="b24db-134">一般に、それぞれ 4 MB より小さい多数のメッセージにサイズの大きいメッセージをフラグメント化されます。</span><span class="sxs-lookup"><span data-stu-id="b24db-134">In general, a large message will be fragmented into numerous messages, each smaller than 4 MB.</span></span> <span data-ttu-id="b24db-135">フラグメント化されるのは本文だけであることを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="b24db-135">It is important to understand that only the body is fragmented.</span></span> <span data-ttu-id="b24db-136">残りのプロパティは各フラグメントと共に送信されます。</span><span class="sxs-lookup"><span data-stu-id="b24db-136">The rest of the properties are sent with each fragment.</span></span>  
  
 <span data-ttu-id="b24db-137">フラグメントの数は、メッセージのサイズとフラグメントのサイズによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="b24db-137">The number of fragments is defined by the size of the message and the size of the fragments.</span></span> <span data-ttu-id="b24db-138">フラグメント サイズは、ファイル Mqrtlarge.dll または BizTalk メッセージ キューの適切な部分によって自動的に決まることもあります。</span><span class="sxs-lookup"><span data-stu-id="b24db-138">The fragment size may be automatically determined by the file Mqrtlarge.dll or the appropriate part of BizTalk Message Queuing.</span></span> <span data-ttu-id="b24db-139">アプリケーションでフラグメント サイズを明示的に指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b24db-139">Applications can also explicitly specify the fragment size.</span></span>  
  
 <span data-ttu-id="b24db-140">サイズの大きいメッセージ用拡張機能では、一定サイズの追加内部データを追加することでメッセージを拡張する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b24db-140">Note that the large message extension requires extending the message by adding additional internal data of a constant size.</span></span>  
  
 <span data-ttu-id="b24db-141">**PROPID_M_EXTENSION**</span><span class="sxs-lookup"><span data-stu-id="b24db-141">**PROPID_M_EXTENSION**</span></span>  
  
 <span data-ttu-id="b24db-142">使用することができます、 **PROPID_M_EXTENSION/PROPID_M_EXTENSION_LEN**プロパティをメッセージに署名します。</span><span class="sxs-lookup"><span data-stu-id="b24db-142">You can use the **PROPID_M_EXTENSION/PROPID_M_EXTENSION_LEN** properties to sign the message.</span></span> <span data-ttu-id="b24db-143">署名は 40 バイト (B) で構成します。</span><span class="sxs-lookup"><span data-stu-id="b24db-143">The signature comprises 40 bytes (B).</span></span> <span data-ttu-id="b24db-144">次の表に、署名のフラグメントを示します。</span><span class="sxs-lookup"><span data-stu-id="b24db-144">The following table shows signature fragments.</span></span>  
  
|<span data-ttu-id="b24db-145">Description</span><span class="sxs-lookup"><span data-stu-id="b24db-145">Description</span></span>|<span data-ttu-id="b24db-146">サイズ</span><span class="sxs-lookup"><span data-stu-id="b24db-146">Size</span></span>|  
|-----------------|----------|  
|<span data-ttu-id="b24db-147">グローバル一意識別子 (GUID) を使用してこのメッセージが送信することを示す**MQSendLargeMessage**</span><span class="sxs-lookup"><span data-stu-id="b24db-147">Globally unique identifier (GUID) denoting that this message was sent using **MQSendLargeMessage**</span></span>|<span data-ttu-id="b24db-148">16 B</span><span class="sxs-lookup"><span data-stu-id="b24db-148">16 B</span></span>|  
|<span data-ttu-id="b24db-149">メッセージの guid を指定しますメッセージのすべての部分に共通する一意の各サイズの大きいメッセージ ID。</span><span class="sxs-lookup"><span data-stu-id="b24db-149">GUID for the message: unique per-large message ID that is common to all parts of the message</span></span>|<span data-ttu-id="b24db-150">16 B</span><span class="sxs-lookup"><span data-stu-id="b24db-150">16 B</span></span>|  
|<span data-ttu-id="b24db-151">サイズの大きいメッセージの合計サイズ</span><span class="sxs-lookup"><span data-stu-id="b24db-151">Total size of the large message</span></span>|<span data-ttu-id="b24db-152">4 B</span><span class="sxs-lookup"><span data-stu-id="b24db-152">4 B</span></span>|  
|<span data-ttu-id="b24db-153">部分番号</span><span class="sxs-lookup"><span data-stu-id="b24db-153">Part number</span></span>|<span data-ttu-id="b24db-154">2 B</span><span class="sxs-lookup"><span data-stu-id="b24db-154">2 B</span></span>|  
|<span data-ttu-id="b24db-155">メッセージ部分の数</span><span class="sxs-lookup"><span data-stu-id="b24db-155">Number of message parts</span></span>|<span data-ttu-id="b24db-156">2 B</span><span class="sxs-lookup"><span data-stu-id="b24db-156">2 B</span></span>|  
  
 <span data-ttu-id="b24db-157">使用するか**PROPID_M_EXTENSION**追加なくなります。</span><span class="sxs-lookup"><span data-stu-id="b24db-157">The decision to use **PROPID_M_EXTENSION** has an additional implication.</span></span> <span data-ttu-id="b24db-158">Microsoft Host Integration Server の MSMQ-MQSeries ブリッジでは、このプロパティを使用して、MQSeries とメッセージ キューのメッセージの間では直接マップされないプロパティを含む構造体を渡します。</span><span class="sxs-lookup"><span data-stu-id="b24db-158">The Microsoft Host Integration Server MSMQ-MQSeries Bridge uses this property to pass a structure that contains properties that are not mapped directly between MQSeries and Message Queuing messages.</span></span> <span data-ttu-id="b24db-159">メッセージを MQSeries に、または MQSeries から送信するアプリケーションは、この構造体を明示的または暗黙的に使用します。</span><span class="sxs-lookup"><span data-stu-id="b24db-159">Applications that send messages to and from MQSeries explicitly or implicitly use this structure.</span></span> <span data-ttu-id="b24db-160">メッセージが受信側アプリケーションでキューから受信されたとき、メッセージ キューでは受信確認を生成することができます。</span><span class="sxs-lookup"><span data-stu-id="b24db-160">Message Queuing can generate acknowledgments when a message has been received from a queue by a receiving application.</span></span> <span data-ttu-id="b24db-161">受信確認は、送信アプリケーションによって指定されたキューに送信されます。</span><span class="sxs-lookup"><span data-stu-id="b24db-161">The acknowledgments are sent to a queue specified by the sending application.</span></span> <span data-ttu-id="b24db-162">サイズの大きいメッセージの場合は、サイズの大きいメッセージの最後の部分についてのみこの受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="b24db-162">In the case of large messages, you send this acknowledgment only for the last part of the large message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b24db-163">参照</span><span class="sxs-lookup"><span data-stu-id="b24db-163">See Also</span></span>  
 [<span data-ttu-id="b24db-164">SDK のユーティリティ</span><span class="sxs-lookup"><span data-stu-id="b24db-164">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)