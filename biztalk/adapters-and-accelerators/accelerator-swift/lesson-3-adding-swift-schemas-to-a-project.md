---
title: 'レッスン 3: SWIFT スキーマをプロジェクトに追加する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, adding to projects
- projects
ms.assetid: e17ef4b8-f060-44cc-b988-0f9f54deab90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba000b90196fb625981244420269274804c24836
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530341"
---
# <a name="lesson-3-adding-swift-schemas-to-a-project"></a><span data-ttu-id="121b7-102">レッスン 3: SWIFT スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="121b7-102">Lesson 3: Adding SWIFT Schemas to a Project</span></span>
<span data-ttu-id="121b7-103">ソリューションと新しいプロジェクトをプロジェクトに項目を追加できます。</span><span class="sxs-lookup"><span data-stu-id="121b7-103">Now that you have a solution and a new project, you can add items to the project.</span></span> <span data-ttu-id="121b7-104">追加する最初の項目は、MT103 SWIFT 支払いメッセージのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="121b7-104">The first item you add is a schema for an MT103 SWIFT Payment message.</span></span> <span data-ttu-id="121b7-105">スキーマ テンプレートを選択すると、BizTalk エディターが起動します。</span><span class="sxs-lookup"><span data-stu-id="121b7-105">When you select the Schema template, BizTalk Editor starts.</span></span>  
  
### <a name="to-add-a-new-schema-to-the-project"></a><span data-ttu-id="121b7-106">新しいスキーマをプロジェクトに追加するには</span><span class="sxs-lookup"><span data-stu-id="121b7-106">To add a new schema to the project</span></span>  
  
1. <span data-ttu-id="121b7-107">ソリューション エクスプ ローラーで右クリックし、 **SWIFTSchemas**プロジェクトをポイントして、**追加**、 をクリックし、**既存項目の**。</span><span class="sxs-lookup"><span data-stu-id="121b7-107">In Solution Explorer, right-click the **SWIFTSchemas** project, point to **Add**, and then click **Existing Item**.</span></span>  
  
2. <span data-ttu-id="121b7-108">追加する既存の項目-SWIFTSchemas ダイアログ ボックスを参照 **\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\<バージョン\>MessagePack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="121b7-108">In the Add Existing Item-SWIFTSchemas dialog box, browse to **\<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> MessagePack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Schemas**.</span></span>  
  
3. <span data-ttu-id="121b7-109">選択、 **SWIFT ベース Types.xsd**と**SWIFT 共通データ Types.xsd**スキーマ、およびクリック**追加**します。</span><span class="sxs-lookup"><span data-stu-id="121b7-109">Select the **SWIFT Base Types.xsd** and the **SWIFT Common Data Types.xsd** schemas, and then click **Add**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="121b7-110">SWIFT のベース Types.xsd と SWIFT の一般的なデータ Types.xsd スキーマ SWIFTSchemas プロジェクトの下でソリューション エクスプ ローラーで表示します。</span><span class="sxs-lookup"><span data-stu-id="121b7-110">The SWIFT Base Types.xsd and the SWIFT Common Data Types.xsd schemas appear in Solution Explorer under the SWIFTSchemas project.</span></span>  
  
4. <span data-ttu-id="121b7-111">ソリューション エクスプ ローラーで右クリックし、 **SWIFTSchemas**プロジェクトをポイントして、**追加**、 をクリックし、**既存項目の**。</span><span class="sxs-lookup"><span data-stu-id="121b7-111">In Solution Explorer, right-click the **SWIFTSchemas** project, point to **Add**, and then click **Existing Item**.</span></span>  
  
5. <span data-ttu-id="121b7-112">追加する既存の項目-SWIFTSchemas ダイアログ ボックスを参照、  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\<バージョン\>MessagePack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Category 1\MT103**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="121b7-112">In the Add Existing Item-SWIFTSchemas dialog box, browse to the **\<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> MessagePack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MT103** folder.</span></span>  
  
6. <span data-ttu-id="121b7-113">選択、 **MT103.xsd**スキーマ、およびクリック**追加**します。</span><span class="sxs-lookup"><span data-stu-id="121b7-113">Select the **MT103.xsd** schema, and then click **Add**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="121b7-114">ソリューション エクスプ ローラーで、SWIFTSchemas プロジェクト MT103.xsd、新しいスキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="121b7-114">The new schema, MT103.xsd, appears in Solution Explorer under the SWIFTSchemas project.</span></span>  
  
7. <span data-ttu-id="121b7-115">ソリューション エクスプ ローラーでダブルクリック**MT103.xsd** BizTalk エディターでスキーマを表示します。</span><span class="sxs-lookup"><span data-stu-id="121b7-115">In Solution Explorer, double-click **MT103.xsd** to view the schema in BizTalk Editor.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="121b7-116">スキーマ ツリー (左側のウィンドウ) と XSD ビュー (右側のウィンドウ) には、BizTalk エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="121b7-116">The schema tree (left pane) and XSD view (right pane) appear in BizTalk Editor.</span></span>  
  
8. <span data-ttu-id="121b7-117">**ファイル** メニューのをクリックして**すべて保存**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="121b7-117">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
   <span data-ttu-id="121b7-118">続行する[レッスン 4。アセンブリの配置のビルドと](../../adapters-and-accelerators/accelerator-swift/lesson-4-building-and-deploying-the-assembly.md)します。</span><span class="sxs-lookup"><span data-stu-id="121b7-118">Proceed to [Lesson 4: Building and Deploying the Assembly](../../adapters-and-accelerators/accelerator-swift/lesson-4-building-and-deploying-the-assembly.md).</span></span>