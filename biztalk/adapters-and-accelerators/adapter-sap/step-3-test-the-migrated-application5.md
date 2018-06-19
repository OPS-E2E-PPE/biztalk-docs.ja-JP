---
title: '手順 3: テスト移行 Application5 |Microsoft ドキュメント'
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
ms.openlocfilehash: 5b5e49968e4b0b463b1665d0752689a14039c2da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217250"
---
# <a name="step-3-test-the-migrated-application"></a><span data-ttu-id="6f5d3-102">手順 3: 移行後のアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="6f5d3-102">Step 3: Test the Migrated Application</span></span>
<span data-ttu-id="6f5d3-103">![手順 3 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="6f5d3-103">![Step 3 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="6f5d3-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="6f5d3-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="6f5d3-105">**目標:** この手順では、WCF ベースを使用してフラット ファイル IDOC を受信して移行したアプリケーションをテストします[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6f5d3-105">**Objective:** In this step, you will test the migrated application by receiving a flat-file IDOC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6f5d3-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="6f5d3-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="6f5d3-107">BizTalk Server 管理コンソールで物理ポートを BizTalk オーケストレーションの論理ポートにマップして、BizTalk アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="6f5d3-107">Configure the BizTalk application by mapping the logical ports in the BizTalk orchestration to physical ports in the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="6f5d3-108">BizTalk を構成する Wcf-custom を使用するアプリケーションを受信ポートを WCF ベースの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6f5d3-108">Configure the BizTalk application to use the WCF-Custom receive port for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
### <a name="to-test-the-migrated-application"></a><span data-ttu-id="6f5d3-109">移行したアプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="6f5d3-109">To test the migrated application</span></span>  
  
1.  <span data-ttu-id="6f5d3-110">SAP GUI を起動し、接続 URI で指定した SAP システムに接続します。</span><span class="sxs-lookup"><span data-stu-id="6f5d3-110">Start the SAP GUI, and connect to the SAP system that you specified in the connection URI.</span></span>  
  
2.  <span data-ttu-id="6f5d3-111">SE37 を実行し、外部システムに IDOC を送信する SAP の関数モジュールを起動します。</span><span class="sxs-lookup"><span data-stu-id="6f5d3-111">Run SE37, and invoke a function module in SAP that sends an IDOC to an external system.</span></span> <span data-ttu-id="6f5d3-112">Wcf-custom 受信ポートの接続 URI で指定されている同じプログラム ID を使用して、IDOC を送信することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6f5d3-112">Make sure you send the IDOC using the same program ID that is specified in the connection URI for the WCF-Custom receive port.</span></span>  
  
3.  <span data-ttu-id="6f5d3-113">オーケストレーションの一部として指定されたファイルの場所で受信 IDOC を探します。</span><span class="sxs-lookup"><span data-stu-id="6f5d3-113">Look for the inbound IDOC at the file location specified as part of the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5d3-114">参照</span><span class="sxs-lookup"><span data-stu-id="6f5d3-114">See Also</span></span>  
 [<span data-ttu-id="6f5d3-115">チュートリアル 4: SAP を移行する BizTalk プロジェクトの IDOC を受信</span><span class="sxs-lookup"><span data-stu-id="6f5d3-115">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)