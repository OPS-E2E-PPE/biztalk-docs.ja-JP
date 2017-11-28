---
title: "レッスン 3: SWIFT スキーマをプロジェクトに追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, adding to projects
- projects
ms.assetid: e17ef4b8-f060-44cc-b988-0f9f54deab90
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2817393a236bf0b33bce34911b7eb52a4b208ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-3-adding-swift-schemas-to-a-project"></a><span data-ttu-id="134bd-102">レッスン 3: SWIFT スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="134bd-102">Lesson 3: Adding SWIFT Schemas to a Project</span></span>
<span data-ttu-id="134bd-103">ソリューションと、新しいプロジェクトがある場合は、これで、プロジェクトに項目を追加できます。</span><span class="sxs-lookup"><span data-stu-id="134bd-103">Now that you have a solution and a new project, you can add items to the project.</span></span> <span data-ttu-id="134bd-104">追加する最初の項目は、MT103 SWIFT 支払いメッセージのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="134bd-104">The first item you add is a schema for an MT103 SWIFT Payment message.</span></span> <span data-ttu-id="134bd-105">スキーマ テンプレートを選択すると、BizTalk エディターが起動します。</span><span class="sxs-lookup"><span data-stu-id="134bd-105">When you select the Schema template, BizTalk Editor starts.</span></span>  
  
### <a name="to-add-a-new-schema-to-the-project"></a><span data-ttu-id="134bd-106">新しいスキーマをプロジェクトに追加するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="134bd-106">To add a new schema to the project</span></span>  
  
1.  <span data-ttu-id="134bd-107">ソリューション エクスプ ローラーで右クリックし、 **SWIFTSchemas**プロジェクトをポイントし、**追加**、順にクリック**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="134bd-107">In Solution Explorer, right-click the **SWIFTSchemas** project, point to **Add**, and then click **Existing Item**.</span></span>  
  
2.  <span data-ttu-id="134bd-108">追加既存項目の SWIFTSchemas ダイアログ ボックスを参照  **\<*ドライブ*>: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > MessagePack\SWIFTMessages\A4SWIFT SRG\<バージョン > \Base スキーマ * *。</span><span class="sxs-lookup"><span data-stu-id="134bd-108">In the Add Existing Item-SWIFTSchemas dialog box, browse to **\<*drive*>:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version> MessagePack\SWIFT Messages\A4SWIFT-SRG\<version>\Base Schemas**.</span></span>  
  
3.  <span data-ttu-id="134bd-109">選択、 **SWIFT ベース Types.xsd**と**SWIFT 共通データ Types.xsd**スキーマ、およびクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="134bd-109">Select the **SWIFT Base Types.xsd** and the **SWIFT Common Data Types.xsd** schemas, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="134bd-110">SWIFT ベース Types.xsd と SWIFT 共通データ Types.xsd スキーマ SWIFTSchemas プロジェクトの下ソリューション エクスプ ローラーで表示します。</span><span class="sxs-lookup"><span data-stu-id="134bd-110">The SWIFT Base Types.xsd and the SWIFT Common Data Types.xsd schemas appear in Solution Explorer under the SWIFTSchemas project.</span></span>  
  
4.  <span data-ttu-id="134bd-111">ソリューション エクスプ ローラーで右クリックし、 **SWIFTSchemas**プロジェクトをポイントし、**追加**、順にクリック**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="134bd-111">In Solution Explorer, right-click the **SWIFTSchemas** project, point to **Add**, and then click **Existing Item**.</span></span>  
  
5.  <span data-ttu-id="134bd-112">追加既存項目の SWIFTSchemas ダイアログ ボックスを参照、   **\<*ドライブ*>: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > MessagePack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Category 1\MT103** フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="134bd-112">In the Add Existing Item-SWIFTSchemas dialog box, browse to the **\<*drive*>:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version> MessagePack\SWIFT Messages\A4SWIFT-SRG\<version>\Category 1\MT103** folder.</span></span>  
  
6.  <span data-ttu-id="134bd-113">選択、 **MT103.xsd**スキーマ、およびクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="134bd-113">Select the **MT103.xsd** schema, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="134bd-114">SWIFTSchemas プロジェクトの下で、ソリューション エクスプ ローラーで、新しいスキーマ MT103.xsd が表示されます。</span><span class="sxs-lookup"><span data-stu-id="134bd-114">The new schema, MT103.xsd, appears in Solution Explorer under the SWIFTSchemas project.</span></span>  
  
7.  <span data-ttu-id="134bd-115">ソリューション エクスプ ローラーで、 **MT103.xsd** BizTalk エディターでスキーマを表示します。</span><span class="sxs-lookup"><span data-stu-id="134bd-115">In Solution Explorer, double-click **MT103.xsd** to view the schema in BizTalk Editor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="134bd-116">(左側のウィンドウ) のスキーマ ツリーと XSD ビュー (右ペイン) には、BizTalk エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="134bd-116">The schema tree (left pane) and XSD view (right pane) appear in BizTalk Editor.</span></span>  
  
8.  <span data-ttu-id="134bd-117">**ファイル** メニューのをクリックして**すべて保存**して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="134bd-117">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
 <span data-ttu-id="134bd-118">進みます[レッスン 4: ビルドしてアセンブリを配置する](../../adapters-and-accelerators/accelerator-swift/lesson-4-building-and-deploying-the-assembly.md)です。</span><span class="sxs-lookup"><span data-stu-id="134bd-118">Proceed to [Lesson 4: Building and Deploying the Assembly](../../adapters-and-accelerators/accelerator-swift/lesson-4-building-and-deploying-the-assembly.md).</span></span>