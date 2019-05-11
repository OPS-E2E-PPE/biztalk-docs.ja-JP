---
title: チュートリアル:SharePoint サイト上の Oracle E-business Suite からのデータの表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1272b76c-29a1-4912-9c2d-8a4cf43df59d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cf80a137a9826328dbf17070119efe8b5398651
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374394"
---
# <a name="tutorial-present-data-from-oracle-e-business-suite-on-a-sharepoint-site"></a><span data-ttu-id="56acb-102">チュートリアル:SharePoint サイト上の Oracle E-business Suite からデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="56acb-102">Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site</span></span>
<span data-ttu-id="56acb-103">このチュートリアルを使用して詳細な手順では、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite から SharePoint ポータルにデータを表示する Microsoft Office SharePoint Server とします。</span><span class="sxs-lookup"><span data-stu-id="56acb-103">This tutorial provides detailed instructions on using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with Microsoft Office SharePoint Server to present data from Oracle E-Business Suite on a SharePoint portal.</span></span> <span data-ttu-id="56acb-104">構成済みの Oracle E-business Suite の成果物の SharePoint portal から、フルテキスト検索を実行することができます、Microsoft Office SharePoint Server での検索アプリケーションを構成する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="56acb-104">It also demonstrates how to configure a search application in the Microsoft Office SharePoint Server that allows you to do a full-text search from a SharePoint portal on the configured Oracle E-Business Suite artifact.</span></span>  
  
 <span data-ttu-id="56acb-105">これを行う方法を示すためには、従業員に関する情報を格納する Oracle E-business Suite では、サンプル インターフェイス テーブルを検討してください。</span><span class="sxs-lookup"><span data-stu-id="56acb-105">To demonstrate how to do so, consider a sample interface table in Oracle E-Business Suite that stores information about employees.</span></span> <span data-ttu-id="56acb-106">このチュートリアルでは、アプリケーションが Microsoft Office SharePoint Server から Oracle E-business Suite を使用して、検索文字列に基づいて顧客の一覧を取得するで作成されます。</span><span class="sxs-lookup"><span data-stu-id="56acb-106">In this tutorial, an application is created in Microsoft Office SharePoint Server that retrieve a list of customers from Oracle E-Business Suite based on a search string using:</span></span>  
  
-   <span data-ttu-id="56acb-107">Microsoft Office SharePoint Server でビジネス データ一覧 Web パーツ</span><span class="sxs-lookup"><span data-stu-id="56acb-107">A Business Data List Web Part in Microsoft Office SharePoint Server</span></span>  
  
-   <span data-ttu-id="56acb-108">Microsoft Office SharePoint Server での検索機能</span><span class="sxs-lookup"><span data-stu-id="56acb-108">The search feature in Microsoft Office SharePoint Server</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56acb-109">このチュートリアルで前を使用するためのすべての前提条件がインストールされているを確認します、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Microsoft Office SharePoint Server の使用。</span><span class="sxs-lookup"><span data-stu-id="56acb-109">Before proceeding with the tutorial, make sure you have installed all the prerequisites for using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="56acb-110">前提条件については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイド、通常 C:\Program files \microsoft BizTalk アダプター Pack\Documents にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="56acb-110">For information about the prerequisites, see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide, typically installed at C:\Program Files\Microsoft BizTalk Adapter Pack\Documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56acb-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="56acb-111">In This Section</span></span>  
  
-   [<span data-ttu-id="56acb-112">ステップ 1: Oracle E-business アダプターを使用して作成および WCF サービスの発行</span><span class="sxs-lookup"><span data-stu-id="56acb-112">Step 1: Use the Oracle E-Business Adapter to Create and Publish a WCF Service</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)  
  
-   [<span data-ttu-id="56acb-113">手順 2:Oracle E-business Suite の成果物用アプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="56acb-113">Step 2: Create an Application Definition File for the Oracle E-Business Suite Artifacts</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)  
  
-   [<span data-ttu-id="56acb-114">ステップ 3:Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="56acb-114">Step 3: Create a SharePoint Application to Retrieve Data from Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)  
  
-   [<span data-ttu-id="56acb-115">手順 4:SharePoint アプリケーションをテストする</span><span class="sxs-lookup"><span data-stu-id="56acb-115">Step 4: Test Your SharePoint Application</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md)