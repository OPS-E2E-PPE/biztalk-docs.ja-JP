---
title: XSD ベース PIP のインポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs, importing
- XSD-based PIPs
- PIPs, XSD-based PIPs
ms.assetid: d12441d4-79bf-4c24-9360-4b78c1da0d34
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d8865d7a75bdb06895b963b8269ed457cd5804f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961656"
---
# <a name="importing-an-xsd-based-pip"></a><span data-ttu-id="a1d05-102">XSD ベース PIP のインポート</span><span class="sxs-lookup"><span data-stu-id="a1d05-102">Importing an XSD-based PIP</span></span>
<span data-ttu-id="a1d05-103">RosettaNet.org によって提供されるほとんどの PIP は DTD ベースですが、新しい PIP は XSD ベースです。</span><span class="sxs-lookup"><span data-stu-id="a1d05-103">While the majority of PIPS provided by RosettaNet.org are DTD-based, newer PIPS are XSD-based.</span></span> <span data-ttu-id="a1d05-104">次の手順では、XSD ベースの PIP をインポートする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a1d05-104">The following procedure describes how to import XSD-based PIPS.</span></span>  
  
### <a name="to-import-an-xsd-based-pip"></a><span data-ttu-id="a1d05-105">XSD ベース PIP のインポートするには</span><span class="sxs-lookup"><span data-stu-id="a1d05-105">To import an XSD-based PIP</span></span>  
  
1.  <span data-ttu-id="a1d05-106">XSD ベース PIP の .zip ファイルに RosettaNet.org からダウンロード[http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859)または CIDX.org から[http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361)です。</span><span class="sxs-lookup"><span data-stu-id="a1d05-106">Download the XSD-based PIP .zip file from RosettaNet.org at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859) or from CIDX.org at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361).</span></span> <span data-ttu-id="a1d05-107">.zip ファイルからファイルを解凍します。</span><span class="sxs-lookup"><span data-stu-id="a1d05-107">Extract the files from the .zip file.</span></span> <span data-ttu-id="a1d05-108">必要なファイルは、XML フォルダーのサブフォルダー内にあります。</span><span class="sxs-lookup"><span data-stu-id="a1d05-108">The files that you need will be in the subfolders of the XML folder.</span></span>  
  
2.  <span data-ttu-id="a1d05-109">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="a1d05-109">Open Visual Studio.</span></span> <span data-ttu-id="a1d05-110">新しい BizTalk プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a1d05-110">Create a new BizTalk project.</span></span>  
  
3.  <span data-ttu-id="a1d05-111">Windows エクスプローラーを開き、手順 1. で解凍した XML フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="a1d05-111">Open Windows Explorer, and move to the XML folder extracted in step 1.</span></span> <span data-ttu-id="a1d05-112">XML フォルダー内の 1 番目のフォルダーを選択し、それを Visual Studio のソリューション エクスプローラーまでドラッグし、作成したプロジェクトにドロップします。</span><span class="sxs-lookup"><span data-stu-id="a1d05-112">Select the first folder under the XML folder, drag it to Solutions Explorer in Visual Studio, and drop it into your project.</span></span> <span data-ttu-id="a1d05-113">XML フォルダー内のすべてのサブフォルダーに対してこの手順を繰り返し、作成したプロジェクトに同じフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="a1d05-113">Repeat for each of the subfolders in the XML folder, creating the same folder structure in your project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a1d05-114">PIP7c7 PIP では、これらのフォルダーには Domain、Interchange、System、および Universal フォルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a1d05-114">For a PIP7c7 PIP these folders would include the Domain, Interchange, System, and Universal folders.</span></span> <span data-ttu-id="a1d05-115">この PIP では、新しく作成したプロジェクトに Domain、Interchange、System、および Universal フォルダーがそのコンテンツと共に作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1d05-115">For this PIP, your project should contain Domain, Interchange, System, and Universal folders and their contents.</span></span>  
  
4.  <span data-ttu-id="a1d05-116">System フォルダーに .xsd ファイルがある場合、ソリューション エクスプローラーでそのファイルを選択し、プロパティ ページに一覧表示されている名前空間を変更します。この操作によって、ファイルに ".System" という文字列は含まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="a1d05-116">If there is an .xsd file in the System folder, select it in Solution Explorer and change the namespace listed in the property page so that it does not contain the string ".System".</span></span> <span data-ttu-id="a1d05-117">たとえば、PIP7c7 PIP で、名前空間を "PIP7c7._System" に変更します。</span><span class="sxs-lookup"><span data-stu-id="a1d05-117">For example, for PIP7c7 PIP, you could change the namespace to be "PIP7c7._System".</span></span> <span data-ttu-id="a1d05-118">System フォルダの各 .xsd ファイルでこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a1d05-118">Repeat for each .xsd file in the System folder.</span></span> <span data-ttu-id="a1d05-119">名前空間を変更しないと、次のようなエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a1d05-119">If you do not change the namespace, you will receive the following or a similar error:</span></span>  
  
    ```  
    The type or namespace name 'SerializableAttribute' does not exist in the class or namespace 'PIP7C7.System'.  
    ```  
  
5.  <span data-ttu-id="a1d05-120">いることを確認するすべての .xsd ファイルを確認、\<スキーマ\>TypeName およびルート ノード TypeName が同一でありません。</span><span class="sxs-lookup"><span data-stu-id="a1d05-120">Review all .xsd files to ensure that the \<schema\> TypeName and root node TypeName are not identical.</span></span> <span data-ttu-id="a1d05-121">たとえば、PIP7C7 PIP の Universal フォルダで PartnerIdentification.xsd が 'partneridentification 'という TypeName の両方、\<スキーマ\>(PartnerIdentification.xsd を選択するとソリューション エクスプ ローラーで) とも、PartnerIdentification ルート ノードです。</span><span class="sxs-lookup"><span data-stu-id="a1d05-121">For example, for a PIP7C7 PIP the PartnerIdentification.xsd in the Universal folder has the TypeName of 'PartnerIdentification' for both the \<schema\> (when PartnerIdentification.xsd is selected in Solution Explorer) and also the PartnerIdentification root node.</span></span> <span data-ttu-id="a1d05-122">この問題を修正するには、ソリューション エクスプローラーで PartnerIdentification.xsd を選択し、プロパティ ページ内で  TypeName プロパティを変更します。この操作によって、TypeName が PartnerIdentification ルート ノードと同一になることを回避できます。</span><span class="sxs-lookup"><span data-stu-id="a1d05-122">To correct this, select PartnerIdentification.xsd in Solution Explorer, and then in the property page change the TypeName property so that it does not contain the same TypeName as the PartnerIdentification root node.</span></span> <span data-ttu-id="a1d05-123">たとえば、TypeName を "_PartnerIdentification" に変更します。</span><span class="sxs-lookup"><span data-stu-id="a1d05-123">For example, change the TypeName to be "_PartnerIdentification".</span></span> <span data-ttu-id="a1d05-124">この手順を実行しないと、プロジェクトのビルドの実行時に次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a1d05-124">If you do not take this step, you will receive the following error when you try to build the project:</span></span>  
  
    ```  
    Node "<Schema>" - This schema file has a TypeName that collides with the RootNode TypeName of one of its root Nodes. Make sure that they are different.  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="a1d05-125">エラー一覧の [ファイル] 列には、どのファイルにこの問題が存在しているかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1d05-125">The File column in the error list will indicate which files have this problem.</span></span>  
  
6.  <span data-ttu-id="a1d05-126">プロジェクトをビルドし、展開します。</span><span class="sxs-lookup"><span data-stu-id="a1d05-126">Build and then deploy the project.</span></span>