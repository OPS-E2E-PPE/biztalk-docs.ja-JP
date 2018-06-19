---
title: FileAct アダプターのセキュリティ アーキテクチャ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5faeebd6-5287-4ac4-a1db-e3c055d323d2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ed8352b788af12fd3c38f489e9ddb65d8375f2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222794"
---
# <a name="fileact-adapter-security-architecture"></a><span data-ttu-id="155fb-102">FileAct アダプターのセキュリティ アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="155fb-102">FileAct Adapter Security Architecture</span></span>
<span data-ttu-id="155fb-103">ファイル送信および受信確認のセキュリティは、SNL と、SAG に固有の証明書と暗号化の機能を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="155fb-103">Security for the file transmission and receipt is implemented using the certificate and crypto features inherent in SNL and the SAG.</span></span>  <span data-ttu-id="155fb-104">証明書などの管理は完全に FileAct アダプターの範囲外です。</span><span class="sxs-lookup"><span data-stu-id="155fb-104">The management of certificates, etc., is completely outside of the scope of the FileAct Adapter.</span></span> <span data-ttu-id="155fb-105">関連付けられた SNL/SAG インスタンスがサービスに登録された、FileAct SWIFT および SNL/SAG に正しくインストールされているソフトウェアと、限り、アダプターは施設を介して SNL Api です。</span><span class="sxs-lookup"><span data-stu-id="155fb-105">As long as the associated SNL/SAG instance is registered for the FileAct service with SWIFT and the software properly installed on SNL/SAG, the adapter makes use of the facilities throught the SNL APIs.</span></span> <span data-ttu-id="155fb-106">FileAct アダプターでは、"Advanced"(ベスト プラクティス) に FACryptoMode は常に設定します。</span><span class="sxs-lookup"><span data-stu-id="155fb-106">The FileAct Adapter will always set the FACryptoMode to “Advanced” (best practice).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="155fb-107">アダプターの場合は、送信ポートごとに個別のセキュリティ コンテキストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="155fb-107">For the adapter, you can create a separate security context for  each send port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="155fb-108">参照</span><span class="sxs-lookup"><span data-stu-id="155fb-108">See Also</span></span>  
 <span data-ttu-id="155fb-109">[FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="155fb-109">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="155fb-110">[FileAct アダプター リアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="155fb-110">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="155fb-111">[FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="155fb-111">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="155fb-112">[FileAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="155fb-112">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="155fb-113">[FileAct アダプター ファイルおよび転送の識別](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="155fb-113">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="155fb-114">[FileAct アダプターをサポートする情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="155fb-114">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="155fb-115">[FileAct アダプター配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="155fb-115">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="155fb-116">FileAct アダプター状態の監視</span><span class="sxs-lookup"><span data-stu-id="155fb-116">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)