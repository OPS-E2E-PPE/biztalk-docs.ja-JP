---
title: 情報の転送をサポートする FileAct アダプター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fc27561-9abb-4496-9db7-f221a6c90738
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5aefba5fe85a8a275d3b2050d8c08cc98f74d06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222818"
---
# <a name="fileact-adapter-supporting-information-transfer"></a><span data-ttu-id="e7b48-102">FileAct アダプターをサポートする情報の転送</span><span class="sxs-lookup"><span data-stu-id="e7b48-102">FileAct Adapter Supporting Information Transfer</span></span>
<span data-ttu-id="e7b48-103">FileAct アダプターは、省略可能なファイルと関連情報の転送を許可します。</span><span class="sxs-lookup"><span data-stu-id="e7b48-103">The FileAct adapter permits the optional transfer of supporting information with files.</span></span> <span data-ttu-id="e7b48-104">この情報は、アプリケーションの判断に転送されます。</span><span class="sxs-lookup"><span data-stu-id="e7b48-104">This information is transferred at the discretion of the application.</span></span> <span data-ttu-id="e7b48-105">アダプターでは、この情報に正しい形式であることを検証を除く元側で特別な処理は行いません。</span><span class="sxs-lookup"><span data-stu-id="e7b48-105">The adapter does not do any special processing of this information on the originating side except to validate that it is in the correct format.</span></span> <span data-ttu-id="e7b48-106">サポート情報を構成する要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e7b48-106">The elements which comprise supporting information include:</span></span>  
  
-   <span data-ttu-id="e7b48-107">ファイルの説明およびファイルの情報</span><span class="sxs-lookup"><span data-stu-id="e7b48-107">File description and file information</span></span>  
  
-   <span data-ttu-id="e7b48-108">情報を転送する転送の説明</span><span class="sxs-lookup"><span data-stu-id="e7b48-108">Transfer description and transfer information</span></span>  
  
-   <span data-ttu-id="e7b48-109">受信確認の説明と受信確認情報</span><span class="sxs-lookup"><span data-stu-id="e7b48-109">Acknowledgement description and acknowledgement information</span></span>  
  
-   <span data-ttu-id="e7b48-110">拒否の説明、および却下の情報</span><span class="sxs-lookup"><span data-stu-id="e7b48-110">Rejection description and reject information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7b48-111">ファイル情報のコンポーネントの 1 つは、圧縮および圧縮解除機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="e7b48-111">One of the components of file information defines compression and decompression.</span></span> <span data-ttu-id="e7b48-112">圧縮および圧縮解除は、アダプターではなく、アプリケーションの責任がします。</span><span class="sxs-lookup"><span data-stu-id="e7b48-112">Compression and decompression are the responsibility of the application, not the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7b48-113">参照</span><span class="sxs-lookup"><span data-stu-id="e7b48-113">See Also</span></span>  
 <span data-ttu-id="e7b48-114">[FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="e7b48-114">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="e7b48-115">[FileAct アダプター リアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="e7b48-115">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="e7b48-116">[FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="e7b48-116">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="e7b48-117">[FileAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="e7b48-117">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="e7b48-118">[FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="e7b48-118">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="e7b48-119">[FileAct アダプター ファイルおよび転送の識別](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="e7b48-119">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="e7b48-120">[FileAct アダプター配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="e7b48-120">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="e7b48-121">FileAct アダプター状態の監視</span><span class="sxs-lookup"><span data-stu-id="e7b48-121">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)