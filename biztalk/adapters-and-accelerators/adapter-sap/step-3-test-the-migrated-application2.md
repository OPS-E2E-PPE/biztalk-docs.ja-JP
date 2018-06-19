---
title: '手順 3: テスト移行 Application2 |Microsoft ドキュメント'
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
ms.openlocfilehash: 6dbf6154337dc9daf5dcfe75b3f5b7299ae843ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216466"
---
# <a name="step-3-test-the-migrated-application"></a><span data-ttu-id="95672-102">手順 3: 移行後のアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="95672-102">Step 3: Test the Migrated Application</span></span>
<span data-ttu-id="95672-103">![手順 3 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="95672-103">![Step 3 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="95672-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="95672-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="95672-105">**目標:** この手順では、WCF ベースを使用してフラット ファイル IDOC を送信することによって移行済みのアプリケーションをテストします[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="95672-105">**Objective:** In this step, you will test the migrated application by sending a flat-file IDOC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="95672-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="95672-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="95672-107">BizTalk Server 管理コンソールで物理ポートを BizTalk オーケストレーションの論理ポートにマップして、BizTalk アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="95672-107">Configure the BizTalk application by mapping the logical ports in the BizTalk orchestration to physical ports in the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="95672-108">WCF ベースの wcf-custom 送信ポートを使用する BizTalk アプリケーションを構成する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="95672-108">Configure the BizTalk application to use the WCF-custom send port for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
### <a name="to-test-the-migrated-application"></a><span data-ttu-id="95672-109">移行したアプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="95672-109">To test the migrated application</span></span>  
  
1.  <span data-ttu-id="95672-110">SendIDOC_Migration フォルダーから BOMDOC.txt ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="95672-110">From the SendIDOC_Migration folder, copy the BOMDOC.txt file.</span></span> <span data-ttu-id="95672-111">これは、フラット ファイル IDOC を SAP システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="95672-111">This is the flat-file IDOC to be sent to the SAP system.</span></span>  
  
2.  <span data-ttu-id="95672-112">貼り付けをファイルにマップされているフォルダーにフラット ファイル IDOC の受信場所。</span><span class="sxs-lookup"><span data-stu-id="95672-112">Paste the flat-file IDOC to the folder that is mapped to the file receive location.</span></span>  
  
3.  <span data-ttu-id="95672-113">オーケストレーションがファイルを使用し、IDOC を SAP システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="95672-113">The orchestration consumes the file and sends the IDOC to the SAP system.</span></span> <span data-ttu-id="95672-114">イベント ビューアーにエラーがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="95672-114">Verify if there are any errors in the event viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95672-115">参照</span><span class="sxs-lookup"><span data-stu-id="95672-115">See Also</span></span>  
 [<span data-ttu-id="95672-116">チュートリアル 3: SAP 送信 IDOC の BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="95672-116">Tutorial 3: Migrating an SAP Send IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)