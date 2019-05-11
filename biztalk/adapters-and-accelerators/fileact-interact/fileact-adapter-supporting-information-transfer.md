---
title: FileAct アダプターの情報の転送をサポートしている |Microsoft Docs
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
ms.openlocfilehash: 49966bac71f9bdd2c825da2869ec81907b90c8c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367153"
---
# <a name="fileact-adapter-supporting-information-transfer"></a><span data-ttu-id="03db2-102">FileAct アダプターのサポート情報の転送</span><span class="sxs-lookup"><span data-stu-id="03db2-102">FileAct Adapter Supporting Information Transfer</span></span>
<span data-ttu-id="03db2-103">FileAct アダプターでは、省略可能なファイルとサポート情報の転送を許可します。</span><span class="sxs-lookup"><span data-stu-id="03db2-103">The FileAct adapter permits the optional transfer of supporting information with files.</span></span> <span data-ttu-id="03db2-104">この情報は、アプリケーションの判断で転送されます。</span><span class="sxs-lookup"><span data-stu-id="03db2-104">This information is transferred at the discretion of the application.</span></span> <span data-ttu-id="03db2-105">アダプターでは、この情報を検証、正しい形式であるを除く元の側での特別な処理は実行しません。</span><span class="sxs-lookup"><span data-stu-id="03db2-105">The adapter does not do any special processing of this information on the originating side except to validate that it is in the correct format.</span></span> <span data-ttu-id="03db2-106">サポート情報を構成する要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="03db2-106">The elements which comprise supporting information include:</span></span>  
  
-   <span data-ttu-id="03db2-107">ファイルの説明とファイルの情報</span><span class="sxs-lookup"><span data-stu-id="03db2-107">File description and file information</span></span>  
  
-   <span data-ttu-id="03db2-108">転送の説明と、情報の移動</span><span class="sxs-lookup"><span data-stu-id="03db2-108">Transfer description and transfer information</span></span>  
  
-   <span data-ttu-id="03db2-109">受信確認の説明と受信確認情報</span><span class="sxs-lookup"><span data-stu-id="03db2-109">Acknowledgement description and acknowledgement information</span></span>  
  
-   <span data-ttu-id="03db2-110">拒否の説明および拒否の情報</span><span class="sxs-lookup"><span data-stu-id="03db2-110">Rejection description and reject information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03db2-111">ファイル情報のコンポーネントの 1 つは、圧縮と圧縮解除を定義します。</span><span class="sxs-lookup"><span data-stu-id="03db2-111">One of the components of file information defines compression and decompression.</span></span> <span data-ttu-id="03db2-112">圧縮と圧縮解除は、アダプターではなく、アプリケーションの役割です。</span><span class="sxs-lookup"><span data-stu-id="03db2-112">Compression and decompression are the responsibility of the application, not the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03db2-113">参照</span><span class="sxs-lookup"><span data-stu-id="03db2-113">See Also</span></span>  
 <span data-ttu-id="03db2-114">[FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="03db2-114">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="03db2-115">[FileAct アダプターのリアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="03db2-115">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="03db2-116">[FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="03db2-116">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="03db2-117">[FileAct アダプターのストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="03db2-117">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="03db2-118">[FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="03db2-118">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="03db2-119">[FileAct アダプター ファイルおよび転送 Id](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="03db2-119">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="03db2-120">[FileAct アダプターの配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="03db2-120">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="03db2-121">FileAct アダプターの状態監視</span><span class="sxs-lookup"><span data-stu-id="03db2-121">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)