---
title: BizTalk での mySAP アダプターを使用する SAP システムから Idoc を送信する |Microsoft Docs
description: ''
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aea8a5e9-d775-4d52-a434-c2908b53cd2d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47b194afbc0fff102c9c3a7017f24610234a88ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372866"
---
# <a name="sending-idocs-from-an-sap-system"></a><span data-ttu-id="b950d-102">SAP システムから Idoc を送信します。</span><span class="sxs-lookup"><span data-stu-id="b950d-102">Sending IDOCs from an SAP System</span></span>
<span data-ttu-id="b950d-103">外部のアプリケーションに、SAP システムから IDOC を送信する SAP システムで完了する高度なタスク。</span><span class="sxs-lookup"><span data-stu-id="b950d-103">High-level tasks to complete on the SAP system to send an IDOC from the SAP system to an external application.</span></span> <span data-ttu-id="b950d-104">これらのタスクを実行するため、SAP 管理者にお問い合わせくださいまたは SAP のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b950d-104">Contact your SAP administrator for performing these tasks or see the SAP guidance.</span></span>  
  
## <a name="send-an-idoc-from-sap"></a><span data-ttu-id="b950d-105">SAP からの IDOC を送信します。</span><span class="sxs-lookup"><span data-stu-id="b950d-105">Send an IDOC from SAP</span></span>  
  
1.  <span data-ttu-id="b950d-106">SAP GUI を起動します。</span><span class="sxs-lookup"><span data-stu-id="b950d-106">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="b950d-107">BD54 トランザクションを使用して論理システムを作成します。</span><span class="sxs-lookup"><span data-stu-id="b950d-107">Create a logical system using BD54 transaction.</span></span>  
  
3.  <span data-ttu-id="b950d-108">SM59 トランザクションを使用して TCP/IP 接続では、RFC 転送先を作成します。</span><span class="sxs-lookup"><span data-stu-id="b950d-108">Create an RFC destination in TCP/IP connections using SM59 transaction.</span></span>  
  
4.  <span data-ttu-id="b950d-109">WE21 トランザクションを使用してポートを作成し、最後の手順で作成された RFC 転送先にアタッチします。</span><span class="sxs-lookup"><span data-stu-id="b950d-109">Create a port using WE21 transaction and attach it to the RFC destination created in the last step.</span></span>  
  
5.  <span data-ttu-id="b950d-110">IDOC の種類と必要なメッセージの種類と WE20 トランザクションを使用してパートナー プロファイルを作成し、最後の手順で作成したポートにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="b950d-110">Create a partner profile using WE20 transaction with the required message type and IDOC type, and then attach it to the port created in the last step.</span></span>  
  
6.  <span data-ttu-id="b950d-111">メッセージの種類を販売トランザクションを使用して、ポートに接続することで、分散型モデルを維持します。</span><span class="sxs-lookup"><span data-stu-id="b950d-111">Maintain a distributed model by connecting the message type to the port using the SALE transaction.</span></span>  
  
7.  <span data-ttu-id="b950d-112">SAP の IDOC を生成します。</span><span class="sxs-lookup"><span data-stu-id="b950d-112">Generate an IDOC within SAP.</span></span> <span data-ttu-id="b950d-113">たとえば、BD10 トランザクションを使用して、MATMAS IDOC をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="b950d-113">For example, use BD10 transaction to trigger a MATMAS IDOC.</span></span> <span data-ttu-id="b950d-114">特定の Idoc をトリガーするには、他のトランザクションについては、SAP 管理者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="b950d-114">Contact your SAP administrator for information about other transactions to trigger specific IDOCs.</span></span>  

## <a name="view-transaction-ids-in-sap"></a><span data-ttu-id="b950d-115">SAP でトランザクション Id の表示</span><span class="sxs-lookup"><span data-stu-id="b950d-115">View Transaction IDs in SAP</span></span>
<span data-ttu-id="b950d-116">ときに、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] tRFC を呼び出すか、IDOC を SAP システムのレジスタの SAP システムにトランザクション ID (TID) の応答で送信します。</span><span class="sxs-lookup"><span data-stu-id="b950d-116">When the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] invokes a tRFC or sends an IDOC to an SAP system, the SAP system registers a transaction ID (TID) in response.</span></span> <span data-ttu-id="b950d-117">一部のシナリオからの呼び出しに対する応答で SAP システムに登録されている TID を把握する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b950d-117">In some scenarios, you might need to know the TID that is registered with the SAP system in response to a call from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="b950d-118">たとえば、問題をトラブルシューティングする SAP システムでの作業 (LUW) の論理単位を識別します。</span><span class="sxs-lookup"><span data-stu-id="b950d-118">For example, you might want to identify the logical unit of work (LUW) on the SAP system to troubleshoot an issue.</span></span>  
  
 <span data-ttu-id="b950d-119">SAP システムで、Tid を表示するには、SM58 トランザクションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b950d-119">To view the TIDs in an SAP system, you must use transaction SM58.</span></span> <span data-ttu-id="b950d-120">SAP 管理者に問い合わせるか、このトランザクションの詳細については、SAP のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b950d-120">Contact your SAP administrator or refer to the SAP guidance for more information about this transaction.</span></span> 

## <a name="view-details-about-idocs-sent-and-received-from-sap"></a><span data-ttu-id="b950d-121">送信され、SAP から受信した Idoc に関する詳細を表示</span><span class="sxs-lookup"><span data-stu-id="b950d-121">View details about IDOCs sent and received from SAP</span></span>
<span data-ttu-id="b950d-122">使用して、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]IDOC を SAP システムに送信または SAP システムから IDOC を受信できます。</span><span class="sxs-lookup"><span data-stu-id="b950d-122">Using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you can send an IDOC to an SAP system or receive an IDOC from an SAP system.</span></span> <span data-ttu-id="b950d-123">状態と送信または受信された IDOC のデータ ビューでの SAP システムを追跡するには、WE02 トランザクションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b950d-123">To track the status and view the data of an IDOC sent or received by an SAP system, you can use transaction WE02.</span></span> <span data-ttu-id="b950d-124">SAP の管理者に問い合わせるか、このトランザクションの詳細については、SAP のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b950d-124">Contact your SAP administrator, or refer to the SAP guidance for more information about this transaction.</span></span>  

  
## <a name="see-also"></a><span data-ttu-id="b950d-125">参照</span><span class="sxs-lookup"><span data-stu-id="b950d-125">See Also</span></span>  
 [<span data-ttu-id="b950d-126">特定の SAP アダプターのシナリオを SAP GUI を使用したタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="b950d-126">Performing Tasks Using the SAP GUI for Specific SAP Adapter Scenarios</span></span>](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)