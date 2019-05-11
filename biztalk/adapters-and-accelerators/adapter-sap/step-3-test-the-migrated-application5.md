---
title: 手順 3:テスト移行 Application5 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (Receive IDOC)
- migration
ms.assetid: 3ad15069-1556-4c0a-8bfd-86704d40c586
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8754056eeb173fc86201a108e95605074101dea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372801"
---
# <a name="step-3-test-the-migrated-application"></a><span data-ttu-id="27403-102">手順 3:移行したアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="27403-102">Step 3: Test the Migrated Application</span></span>
<span data-ttu-id="27403-103">![ステップ 3/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="27403-103">![Step 3 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="27403-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="27403-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="27403-105">**目標:** この手順では、WCF ベースを使用してフラット ファイル IDOC を受信することによって、移行済みのアプリケーションをテストします[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="27403-105">**Objective:** In this step, you will test the migrated application by receiving a flat-file IDOC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="27403-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="27403-106">Prerequisites</span></span>  
  
- <span data-ttu-id="27403-107">BizTalk アプリケーションを構成するには、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマッピングします。</span><span class="sxs-lookup"><span data-stu-id="27403-107">Configure the BizTalk application by mapping the logical ports in the BizTalk orchestration to physical ports in the BizTalk Server Administration console.</span></span>  
  
- <span data-ttu-id="27403-108">構成、BizTalk WCF カスタムを使用するアプリケーションが WCF ベースのポートを受信[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="27403-108">Configure the BizTalk application to use the WCF-Custom receive port for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
### <a name="to-test-the-migrated-application"></a><span data-ttu-id="27403-109">移行したアプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="27403-109">To test the migrated application</span></span>  
  
1.  <span data-ttu-id="27403-110">SAP の GUI を起動し、接続 URI で指定した SAP システムに接続します。</span><span class="sxs-lookup"><span data-stu-id="27403-110">Start the SAP GUI, and connect to the SAP system that you specified in the connection URI.</span></span>  
  
2.  <span data-ttu-id="27403-111">SE37 を実行して、sap の IDOC を外部システムに送信する関数モジュールを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="27403-111">Run SE37, and invoke a function module in SAP that sends an IDOC to an external system.</span></span> <span data-ttu-id="27403-112">Wcf-custom の受信ポートの接続 URI で指定されている同じプログラム ID を使用して IDOC を送信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="27403-112">Make sure you send the IDOC using the same program ID that is specified in the connection URI for the WCF-Custom receive port.</span></span>  
  
3.  <span data-ttu-id="27403-113">オーケストレーションの一部として指定されたファイルの場所で受信 IDOC を探します。</span><span class="sxs-lookup"><span data-stu-id="27403-113">Look for the inbound IDOC at the file location specified as part of the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27403-114">参照</span><span class="sxs-lookup"><span data-stu-id="27403-114">See Also</span></span>  
 [<span data-ttu-id="27403-115">チュートリアル 4: SAP の IDOC 受信 BizTalk プロジェクトを移行する</span><span class="sxs-lookup"><span data-stu-id="27403-115">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)