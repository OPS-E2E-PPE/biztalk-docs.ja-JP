---
title: XSD ベース PIP のインポート |Microsoft Docs
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
ms.openlocfilehash: b8d1a0d6b4fe835a38dc5eaf19a328b14e0d288f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283667"
---
# <a name="importing-an-xsd-based-pip"></a><span data-ttu-id="51d83-102">XSD ベース PIP のインポート</span><span class="sxs-lookup"><span data-stu-id="51d83-102">Importing an XSD-based PIP</span></span>
<span data-ttu-id="51d83-103">ほとんどの PIP を RosettaNet.org によって提供されるは DTD ベース、新しい PIP は XSD ベースです。</span><span class="sxs-lookup"><span data-stu-id="51d83-103">While the majority of PIPS provided by RosettaNet.org are DTD-based, newer PIPS are XSD-based.</span></span> <span data-ttu-id="51d83-104">次の手順では、XSD ベース PIP をインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="51d83-104">The following procedure describes how to import XSD-based PIPS.</span></span>  
  
### <a name="to-import-an-xsd-based-pip"></a><span data-ttu-id="51d83-105">XSD ベース PIP をインポートするには</span><span class="sxs-lookup"><span data-stu-id="51d83-105">To import an XSD-based PIP</span></span>  
  
1.  <span data-ttu-id="51d83-106">XSD ベース PIP の .zip ファイルをダウンロードで RosettaNet.org からダウンロードした[ http://go.microsoft.com/FWLink/?LinkID=33859 ](http://go.microsoft.com/FWLink/?LinkID=33859)または CIDX.org から[ http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361)します。</span><span class="sxs-lookup"><span data-stu-id="51d83-106">Download the XSD-based PIP .zip file from RosettaNet.org at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859) or from CIDX.org at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361).</span></span> <span data-ttu-id="51d83-107">.Zip ファイルからファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="51d83-107">Extract the files from the .zip file.</span></span> <span data-ttu-id="51d83-108">必要なファイルは、XML フォルダーのサブフォルダーになります。</span><span class="sxs-lookup"><span data-stu-id="51d83-108">The files that you need will be in the subfolders of the XML folder.</span></span>  
  
2.  <span data-ttu-id="51d83-109">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="51d83-109">Open Visual Studio.</span></span> <span data-ttu-id="51d83-110">新しい BizTalk プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="51d83-110">Create a new BizTalk project.</span></span>  
  
3.  <span data-ttu-id="51d83-111">Windows エクスプ ローラーを開き、手順 1. で解凍した XML フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="51d83-111">Open Windows Explorer, and move to the XML folder extracted in step 1.</span></span> <span data-ttu-id="51d83-112">XML フォルダーの下の最初のフォルダーを選択、Visual Studio で、ソリューション エクスプ ローラーにドラッグし、プロジェクトにドロップします。</span><span class="sxs-lookup"><span data-stu-id="51d83-112">Select the first folder under the XML folder, drag it to Solutions Explorer in Visual Studio, and drop it into your project.</span></span> <span data-ttu-id="51d83-113">プロジェクトと同じフォルダー構造を作成する、XML フォルダー内のサブフォルダーのごとに繰り返します。</span><span class="sxs-lookup"><span data-stu-id="51d83-113">Repeat for each of the subfolders in the XML folder, creating the same folder structure in your project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51d83-114">PIP7c7 PIP のこれらのフォルダーが、ドメイン、インターチェンジ、システム、および Universal フォルダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="51d83-114">For a PIP7c7 PIP these folders would include the Domain, Interchange, System, and Universal folders.</span></span> <span data-ttu-id="51d83-115">この pip では、プロジェクトは、ドメイン、インターチェンジ、システム、および Universal フォルダーとその内容を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="51d83-115">For this PIP, your project should contain Domain, Interchange, System, and Universal folders and their contents.</span></span>  
  
4.  <span data-ttu-id="51d83-116">システム フォルダーに .xsd ファイルがある場合は、ソリューション エクスプ ローラーで選択してプロパティ ページには、文字列が含まれていないように表示する名前空間を変更"。システム"。</span><span class="sxs-lookup"><span data-stu-id="51d83-116">If there is an .xsd file in the System folder, select it in Solution Explorer and change the namespace listed in the property page so that it does not contain the string ".System".</span></span> <span data-ttu-id="51d83-117">たとえば、PIP7c7 pip で"pip7c7._system"に名前空間を変更します。</span><span class="sxs-lookup"><span data-stu-id="51d83-117">For example, for PIP7c7 PIP, you could change the namespace to be "PIP7c7._System".</span></span> <span data-ttu-id="51d83-118">システム フォルダー内の各 .xsd ファイルに対して繰り返します。</span><span class="sxs-lookup"><span data-stu-id="51d83-118">Repeat for each .xsd file in the System folder.</span></span> <span data-ttu-id="51d83-119">名前空間を変更しない場合または、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51d83-119">If you do not change the namespace, you will receive the following or a similar error:</span></span>  
  
    ```  
    The type or namespace name 'SerializableAttribute' does not exist in the class or namespace 'PIP7C7.System'.  
    ```  
  
5.  <span data-ttu-id="51d83-120">いることを確認するすべての .xsd ファイルを確認、\<スキーマ\>TypeName およびルート ノード TypeName が同一でないです。</span><span class="sxs-lookup"><span data-stu-id="51d83-120">Review all .xsd files to ensure that the \<schema\> TypeName and root node TypeName are not identical.</span></span> <span data-ttu-id="51d83-121">たとえば、PIP7C7 PIP の Universal フォルダで PartnerIdentification.xsd が 'partneridentification 'という TypeName 両方の\<スキーマ\>(PartnerIdentification.xsd を選択するとソリューション エクスプ ローラーで) とも、PartnerIdentification ルート ノードです。</span><span class="sxs-lookup"><span data-stu-id="51d83-121">For example, for a PIP7C7 PIP the PartnerIdentification.xsd in the Universal folder has the TypeName of 'PartnerIdentification' for both the \<schema\> (when PartnerIdentification.xsd is selected in Solution Explorer) and also the PartnerIdentification root node.</span></span> <span data-ttu-id="51d83-122">これを修正するには、ソリューション エクスプ ローラーで PartnerIdentification.xsd を選択し、プロパティ ページで変更 TypeName プロパティ PartnerIdentification ルート ノードとして同じ型名が含まれていないようにします。</span><span class="sxs-lookup"><span data-stu-id="51d83-122">To correct this, select PartnerIdentification.xsd in Solution Explorer, and then in the property page change the TypeName property so that it does not contain the same TypeName as the PartnerIdentification root node.</span></span> <span data-ttu-id="51d83-123">たとえば、TypeName を"_partneridentification"を変更します。</span><span class="sxs-lookup"><span data-stu-id="51d83-123">For example, change the TypeName to be "_PartnerIdentification".</span></span> <span data-ttu-id="51d83-124">この手順を実行しない場合、プロジェクトをビルドするときに、次のエラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="51d83-124">If you do not take this step, you will receive the following error when you try to build the project:</span></span>  
  
    ```  
    Node "<Schema>" - This schema file has a TypeName that collides with the RootNode TypeName of one of its root Nodes. Make sure that they are different.  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="51d83-125">エラー一覧 に ファイル 列では、この問題があるファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="51d83-125">The File column in the error list will indicate which files have this problem.</span></span>  
  
6.  <span data-ttu-id="51d83-126">ビルドし、プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="51d83-126">Build and then deploy the project.</span></span>