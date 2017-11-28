---
title: "FileAct アダプター ファイルと転送 Id |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a9aaff1-8816-42cf-b100-fedf964caaf5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5340f9ad739009ff1cb1257365ceeeb7459511a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="fileact-adapter-file-and-transfer-identification"></a><span data-ttu-id="d8798-102">FileAct アダプター ファイルおよび転送の識別</span><span class="sxs-lookup"><span data-stu-id="d8798-102">FileAct Adapter File and Transfer Identification</span></span>
<span data-ttu-id="d8798-103">A4SWIFT FileAct アダプターにより、開発者は実行時にファイル サービスおよび転送の識別の詳細を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d8798-103">The A4SWIFT FileAct adapter permits the developer to supply file and transfer identification specifics at runtime.</span></span> <span data-ttu-id="d8798-104">これらのパラメーターを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d8798-104">These parameters include the following:</span></span>  
  
-   <span data-ttu-id="d8798-105">**物理ファイル名**– 完全なパスと読み取りまたは書き込みするファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="d8798-105">**Physical file name** – the full path and name of the file to be read or written.</span></span> <span data-ttu-id="d8798-106">このパラメーターが渡されないと、ファイル ハンドラー コンポーネントのローカルです。</span><span class="sxs-lookup"><span data-stu-id="d8798-106">This parameter is never passed, and is local to the file handler component.</span></span>  
  
-   <span data-ttu-id="d8798-107">**論理ファイル名**– SWIFTNet 間で、受信アプリケーションへの送信元アプリケーションからファイル名が渡されます。</span><span class="sxs-lookup"><span data-stu-id="d8798-107">**Logical file name** – the file name passed from the sending application to the receiving application across SWIFTNet.</span></span> <span data-ttu-id="d8798-108">これは省略可能であり、パスを除いた物理ファイル名が使用されます指定されていない場合。</span><span class="sxs-lookup"><span data-stu-id="d8798-108">This is optional, and, if not supplied, the physical file name without the path is used.</span></span>  
  
-   <span data-ttu-id="d8798-109">**ファイル転送イベント エンドポイント**– サブスクライブ イベント プリミティブでファイル転送イベント処理アプリケーションに指定した名前です。</span><span class="sxs-lookup"><span data-stu-id="d8798-109">**File transfer event endpoint** – the name specified in the Subscribe Event primitive by the application handling the file transfer events.</span></span> <span data-ttu-id="d8798-110">このパラメーターは、ファイルの転送をイベントのレポートを受信するアプリケーションにリンクします。</span><span class="sxs-lookup"><span data-stu-id="d8798-110">This parameter links the file transfer to the application which receives the event reports.</span></span>  
  
-   <span data-ttu-id="d8798-111">**ファイル転送参照**– トークン文字列が作成され、転送のハンドルとして FileAct サブシステムによって使用自体です。</span><span class="sxs-lookup"><span data-stu-id="d8798-111">**File Transfer Reference** – a token string created and used by the FileAct subsystem as a handle on the transfer, itself.</span></span> <span data-ttu-id="d8798-112">これは、限り FileAct アダプターは、単なる文字列この譲渡に固有です。</span><span class="sxs-lookup"><span data-stu-id="d8798-112">This is simply a string unique to this transfer, as far as the FileAct adapter is concerned.</span></span>  
  
-   <span data-ttu-id="d8798-113">**キーを転送**– の転送を識別する、アプリケーションによって割り当てられた文字列は、目的を中止します。</span><span class="sxs-lookup"><span data-stu-id="d8798-113">**Transfer Key** – a string assigned by the application to identify the transfer for abort purposes.</span></span> <span data-ttu-id="d8798-114">指定しない場合、アプリケーションで、これは、ファイルに関連付けられている GUID です。</span><span class="sxs-lookup"><span data-stu-id="d8798-114">If not provided by the application, this is the GUID associated with the file.</span></span>  
  
-   <span data-ttu-id="d8798-115">**パーティションを転送**– 複数の転送を関連付けるために使用する文字列。</span><span class="sxs-lookup"><span data-stu-id="d8798-115">**Transfer Partition** – a string used to relate multiple transfers.</span></span> <span data-ttu-id="d8798-116">指定しない場合、呼び出しで、開発者が、この関連の送信を定義するときに指定された「アプリケーション名」またはされる受信場所。</span><span class="sxs-lookup"><span data-stu-id="d8798-116">If not supplied in the calls by the developer, this will be the “Application Name” specified when defining the relevant send or receive location.</span></span>  
  
-   <span data-ttu-id="d8798-117">**ユーザーの参照**– 否認不可の転送を一意に識別する、アプリケーションで定義されている文字列。</span><span class="sxs-lookup"><span data-stu-id="d8798-117">**User Reference** – a string defined by the application to uniquely identify the transfer for non-repudiation.</span></span> <span data-ttu-id="d8798-118">指定しない場合、アプリケーションで、ファイルに関連付けられている GUID になります。</span><span class="sxs-lookup"><span data-stu-id="d8798-118">If not provided by the application, this will be the GUID associated with the file.</span></span>  
  
-   <span data-ttu-id="d8798-119">**メッセージ ID** – 最初の要求または応答を一意に定義の識別子。</span><span class="sxs-lookup"><span data-stu-id="d8798-119">**Message ID** – the identifier uniquely defining the initial request or response.</span></span> <span data-ttu-id="d8798-120">これは、送信アダプターによって生成されるたびに、適切な要求または応答メッセージに関連付けられた GUID です。</span><span class="sxs-lookup"><span data-stu-id="d8798-120">This is the GUID associated with the appropriate request or response message, as generated by the sending adapter.</span></span> <span data-ttu-id="d8798-121">したがって、クライアントが要求のメッセージ ID を生成し、サーバーがその応答します。</span><span class="sxs-lookup"><span data-stu-id="d8798-121">Thus, the client generates the Message ID for requests and the server does so for responses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8798-122">参照</span><span class="sxs-lookup"><span data-stu-id="d8798-122">See Also</span></span>  
 <span data-ttu-id="d8798-123">[FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="d8798-123">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="d8798-124">[FileAct アダプター リアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="d8798-124">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="d8798-125">[FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="d8798-125">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="d8798-126">[FileAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="d8798-126">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="d8798-127">[FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="d8798-127">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="d8798-128">[FileAct アダプターをサポートする情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="d8798-128">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="d8798-129">[FileAct アダプター配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="d8798-129">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="d8798-130">FileAct アダプター状態の監視</span><span class="sxs-lookup"><span data-stu-id="d8798-130">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)