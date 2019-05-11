---
title: FileAct アダプター ファイルおよび転送 Id |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a9aaff1-8816-42cf-b100-fedf964caaf5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4530a524518c96db0b42cbae456ba6705e2e9b0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367197"
---
# <a name="fileact-adapter-file-and-transfer-identification"></a><span data-ttu-id="9f053-102">FileAct アダプター ファイルおよび転送 Id</span><span class="sxs-lookup"><span data-stu-id="9f053-102">FileAct Adapter File and Transfer Identification</span></span>
<span data-ttu-id="9f053-103">A4SWIFT FileAct アダプターでは、実行時にファイルおよび転送の識別の詳細を指定する、開発者が許可されます。</span><span class="sxs-lookup"><span data-stu-id="9f053-103">The A4SWIFT FileAct adapter permits the developer to supply file and transfer identification specifics at runtime.</span></span> <span data-ttu-id="9f053-104">これらのパラメーターを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="9f053-104">These parameters include the following:</span></span>  
  
-   <span data-ttu-id="9f053-105">**物理ファイル名**– 読み取りまたは書き込みするファイルの名前と完全なパス。</span><span class="sxs-lookup"><span data-stu-id="9f053-105">**Physical file name** – the full path and name of the file to be read or written.</span></span> <span data-ttu-id="9f053-106">このパラメーターが渡されないとは、ファイル ハンドラー コンポーネントに対してローカルです。</span><span class="sxs-lookup"><span data-stu-id="9f053-106">This parameter is never passed, and is local to the file handler component.</span></span>  
  
-   <span data-ttu-id="9f053-107">**論理ファイル名**– SWIFTNet 間で、受信アプリケーションへの送信元アプリケーションからファイル名が渡されます。</span><span class="sxs-lookup"><span data-stu-id="9f053-107">**Logical file name** – the file name passed from the sending application to the receiving application across SWIFTNet.</span></span> <span data-ttu-id="9f053-108">これは省略可能でと、指定しない場合、パスを使用せずに物理ファイル名が使用します。</span><span class="sxs-lookup"><span data-stu-id="9f053-108">This is optional, and, if not supplied, the physical file name without the path is used.</span></span>  
  
-   <span data-ttu-id="9f053-109">**ファイル転送イベント エンドポイント**– プリミティブのイベントのサブスクライブでファイル転送イベントを処理するアプリケーションで指定された名前。</span><span class="sxs-lookup"><span data-stu-id="9f053-109">**File transfer event endpoint** – the name specified in the Subscribe Event primitive by the application handling the file transfer events.</span></span> <span data-ttu-id="9f053-110">このパラメーターは、イベントのレポートを受信するアプリケーションにファイル転送をリンクします。</span><span class="sxs-lookup"><span data-stu-id="9f053-110">This parameter links the file transfer to the application which receives the event reports.</span></span>  
  
-   <span data-ttu-id="9f053-111">**ファイル転送参照**– トークン文字列が作成され、それ自体、転送のハンドルとして FileAct サブシステムで使用します。</span><span class="sxs-lookup"><span data-stu-id="9f053-111">**File Transfer Reference** – a token string created and used by the FileAct subsystem as a handle on the transfer, itself.</span></span> <span data-ttu-id="9f053-112">FileAct アダプターのに関する限り、この移行に固有の文字列だけです。</span><span class="sxs-lookup"><span data-stu-id="9f053-112">This is simply a string unique to this transfer, as far as the FileAct adapter is concerned.</span></span>  
  
-   <span data-ttu-id="9f053-113">**キーを転送**– の転送を識別するためにアプリケーションによって割り当てられた文字列は、目的を中止します。</span><span class="sxs-lookup"><span data-stu-id="9f053-113">**Transfer Key** – a string assigned by the application to identify the transfer for abort purposes.</span></span> <span data-ttu-id="9f053-114">アプリケーションで指定されていない場合、ファイルに関連付けられた GUID になります。</span><span class="sxs-lookup"><span data-stu-id="9f053-114">If not provided by the application, this is the GUID associated with the file.</span></span>  
  
-   <span data-ttu-id="9f053-115">**パーティションを転送**– 複数の転送を関連付けに使用する文字列。</span><span class="sxs-lookup"><span data-stu-id="9f053-115">**Transfer Partition** – a string used to relate multiple transfers.</span></span> <span data-ttu-id="9f053-116">指定しない場合、呼び出しで開発者が、これを"Application Name"、関連する送信の定義時に指定するまたは受信場所します。</span><span class="sxs-lookup"><span data-stu-id="9f053-116">If not supplied in the calls by the developer, this will be the “Application Name” specified when defining the relevant send or receive location.</span></span>  
  
-   <span data-ttu-id="9f053-117">**ユーザー参照**– 非否認の転送を一意に識別するアプリケーションで定義されている文字列。</span><span class="sxs-lookup"><span data-stu-id="9f053-117">**User Reference** – a string defined by the application to uniquely identify the transfer for non-repudiation.</span></span> <span data-ttu-id="9f053-118">アプリケーションで指定されていない場合、ファイルに関連付けられた GUID になります。</span><span class="sxs-lookup"><span data-stu-id="9f053-118">If not provided by the application, this will be the GUID associated with the file.</span></span>  
  
-   <span data-ttu-id="9f053-119">**メッセージ ID** – 最初の要求または応答を一意に定義する識別子。</span><span class="sxs-lookup"><span data-stu-id="9f053-119">**Message ID** – the identifier uniquely defining the initial request or response.</span></span> <span data-ttu-id="9f053-120">これは、送信アダプターによって生成されると、適切な要求または応答メッセージに関連付けられた GUID です。</span><span class="sxs-lookup"><span data-stu-id="9f053-120">This is the GUID associated with the appropriate request or response message, as generated by the sending adapter.</span></span> <span data-ttu-id="9f053-121">したがって、クライアントは要求のメッセージ ID を生成し、サーバーは応答の。</span><span class="sxs-lookup"><span data-stu-id="9f053-121">Thus, the client generates the Message ID for requests and the server does so for responses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f053-122">参照</span><span class="sxs-lookup"><span data-stu-id="9f053-122">See Also</span></span>  
 <span data-ttu-id="9f053-123">[FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="9f053-123">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="9f053-124">[FileAct アダプターのリアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="9f053-124">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="9f053-125">[FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="9f053-125">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="9f053-126">[FileAct アダプターのストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="9f053-126">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="9f053-127">[FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="9f053-127">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="9f053-128">[FileAct アダプターのサポート情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="9f053-128">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="9f053-129">[FileAct アダプターの配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="9f053-129">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="9f053-130">FileAct アダプターの状態監視</span><span class="sxs-lookup"><span data-stu-id="9f053-130">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)