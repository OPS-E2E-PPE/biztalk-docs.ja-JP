---
title: '手順 3: 移行後のアプリケーション 2 のテスト |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (Send IDOC)
- migration
ms.assetid: 8dc0d127-71ce-4668-a3bf-c893a8f6848d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc49906e58e549a8ed9c90446b011dc3b51e0a45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017818"
---
# <a name="step-3-test-the-migrated-application"></a><span data-ttu-id="21938-102">手順 3: 移行後のアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="21938-102">Step 3: Test the Migrated Application</span></span>
<span data-ttu-id="21938-103">![ステップ 3/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="21938-103">![Step 3 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="21938-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="21938-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="21938-105">**目標:** この手順では、WCF ベースを使用してフラット ファイル IDOC を送信することによって移行済みのアプリケーションをテストします[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="21938-105">**Objective:** In this step, you will test the migrated application by sending a flat-file IDOC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="21938-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="21938-106">Prerequisites</span></span>  
  
- <span data-ttu-id="21938-107">BizTalk アプリケーションを構成するには、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマッピングします。</span><span class="sxs-lookup"><span data-stu-id="21938-107">Configure the BizTalk application by mapping the logical ports in the BizTalk orchestration to physical ports in the BizTalk Server Administration console.</span></span>  
  
- <span data-ttu-id="21938-108">WCF ベースの wcf-custom 送信ポートを使用する BizTalk アプリケーションを構成する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="21938-108">Configure the BizTalk application to use the WCF-custom send port for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
### <a name="to-test-the-migrated-application"></a><span data-ttu-id="21938-109">移行したアプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="21938-109">To test the migrated application</span></span>  
  
1.  <span data-ttu-id="21938-110">SendIDOC_Migration フォルダーから BOMDOC.txt ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="21938-110">From the SendIDOC_Migration folder, copy the BOMDOC.txt file.</span></span> <span data-ttu-id="21938-111">これは、SAP システムに送信するフラット ファイル IDOC です。</span><span class="sxs-lookup"><span data-stu-id="21938-111">This is the flat-file IDOC to be sent to the SAP system.</span></span>  
  
2.  <span data-ttu-id="21938-112">貼り付け、ファイルにマップされているフォルダーにフラット ファイル IDOC の受信場所。</span><span class="sxs-lookup"><span data-stu-id="21938-112">Paste the flat-file IDOC to the folder that is mapped to the file receive location.</span></span>  
  
3.  <span data-ttu-id="21938-113">オーケストレーションは、ファイルを使用し、IDOC を SAP システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="21938-113">The orchestration consumes the file and sends the IDOC to the SAP system.</span></span> <span data-ttu-id="21938-114">イベント ビューアーにエラーがあるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="21938-114">Verify if there are any errors in the event viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21938-115">参照</span><span class="sxs-lookup"><span data-stu-id="21938-115">See Also</span></span>  
 [<span data-ttu-id="21938-116">チュートリアル 3: SAP の IDOC 送信 BizTalk プロジェクトを移行する</span><span class="sxs-lookup"><span data-stu-id="21938-116">Tutorial 3: Migrating an SAP Send IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)