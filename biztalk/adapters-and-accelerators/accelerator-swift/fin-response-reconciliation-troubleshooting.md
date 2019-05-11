---
title: FIN Response Reconciliation のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, troubleshooting
- troubleshooting, FIN Response Reconciliation
ms.assetid: f62326aa-9a4e-4941-a9bb-20bde980f99e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9fa60b9b9f3034e795c191cc6a40e7288f195ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377805"
---
# <a name="fin-response-reconciliation-troubleshooting"></a><span data-ttu-id="1e6e8-102">FIN Response Reconciliation のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1e6e8-102">FIN Response Reconciliation Troubleshooting</span></span>
## <a name="the-frr-bam-view-does-not-show-the-message-type-of-a-message"></a><span data-ttu-id="1e6e8-103">FRR BAM ビューは、メッセージのメッセージの種類を表示しません。</span><span class="sxs-lookup"><span data-stu-id="1e6e8-103">The FRR BAM view does not show the message type of a message</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1e6e8-104">現象</span><span class="sxs-lookup"><span data-stu-id="1e6e8-104">Symptom</span></span>  
 <span data-ttu-id="1e6e8-105">MRSR サイト FRR BAM ビューには、1 つまたは複数のメッセージのメッセージの種類は表示されません。</span><span class="sxs-lookup"><span data-stu-id="1e6e8-105">The FRR BAM view in MRSR site does not show the message type for one or more messages.</span></span> <span data-ttu-id="1e6e8-106">メッセージまたはメッセージの他のすべてのデータが表示され、メッセージの種類がに対して表示されるその他のすべてのメッセージ型のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="1e6e8-106">All other data for the message or messages is shown, and the message type is shown for instances of all other message types.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1e6e8-107">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1e6e8-107">Possible Cause</span></span>  
 <span data-ttu-id="1e6e8-108">FRRMessageOut アクティビティでは、F21 メッセージ (Ack/NAKs) のメッセージの種類は記録されません。</span><span class="sxs-lookup"><span data-stu-id="1e6e8-108">The FRRMessageOut activity does not record the message type for F21 messages (ACKs/NAKs).</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1e6e8-109">ソリューション</span><span class="sxs-lookup"><span data-stu-id="1e6e8-109">Solution</span></span>  
 <span data-ttu-id="1e6e8-110">この問題が発生した場合は、MRSR サイト F21 メッセージとして FRR BAM ビューで表示されているメッセージの種類がないすべてのメッセージを解釈します。</span><span class="sxs-lookup"><span data-stu-id="1e6e8-110">If you encounter this problem, interpret any message that does not have a message type listed in the FRR BAM view in MRSR site as an F21 message.</span></span>  
  
## <a name="deploying-system-level-schemas-in-a-project-generates-an-error"></a><span data-ttu-id="1e6e8-111">プロジェクトでシステム レベルのスキーマを展開するには、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1e6e8-111">Deploying system-level schemas in a project generates an error</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1e6e8-112">現象</span><span class="sxs-lookup"><span data-stu-id="1e6e8-112">Symptom</span></span>  
 <span data-ttu-id="1e6e8-113">プロジェクトで FrrSchemas.dll でシステム レベルのスキーマを展開しようとしたときにエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e6e8-113">When you attempt to deploy the system-level schemas in FrrSchemas.dll in a project, you receive an error.</span></span> <span data-ttu-id="1e6e8-114">これらのスキーマの一覧は、次を参照してください。 [FIN 応答の種類](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="1e6e8-114">For a list of these schemas, see [FIN Response Types](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md).</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1e6e8-115">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1e6e8-115">Possible Cause</span></span>  
 <span data-ttu-id="1e6e8-116">FrrSchemas.dll でシステム レベルのスキーマは、FrrSchemas.dll に既に展開されています。</span><span class="sxs-lookup"><span data-stu-id="1e6e8-116">The system-level schemas in FrrSchemas.dll are already deployed in FrrSchemas.dll.</span></span> <span data-ttu-id="1e6e8-117">再度展開エラーが発生しようとしています。</span><span class="sxs-lookup"><span data-stu-id="1e6e8-117">Trying to deploy them again results in an error.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1e6e8-118">ソリューション</span><span class="sxs-lookup"><span data-stu-id="1e6e8-118">Solution</span></span>  
 <span data-ttu-id="1e6e8-119">FrrSchemas.dll でシステム レベルのスキーマを展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1e6e8-119">There is no need to deploy the system-level schemas in FrrSchemas.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e6e8-120">参照</span><span class="sxs-lookup"><span data-stu-id="1e6e8-120">See Also</span></span>  
 [<span data-ttu-id="1e6e8-121">トラブルシューティング: 問題と解決方法</span><span class="sxs-lookup"><span data-stu-id="1e6e8-121">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)