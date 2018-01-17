---
title: "XML メッセージ用スキーマを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0270293-fe23-42bd-b090-e877d5e9ce0b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6396d4607e93298961e6691ded2ca8d4566d819c
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-create-schemas-for-xml-messages"></a><span data-ttu-id="a2f86-102">XML メッセージ用スキーマの作成方法</span><span class="sxs-lookup"><span data-stu-id="a2f86-102">How to Create Schemas for XML Messages</span></span>
<span data-ttu-id="a2f86-103">BizTalk メッセージのスキーマは、複数の方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="a2f86-103">There are several methods for creating BizTalk message schemas.</span></span> <span data-ttu-id="a2f86-104">このトピックでは、いくつかの方法について手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="a2f86-104">This topic provides step-by-step instructions for some of those methods.</span></span>  
  
### <a name="to-create-a-new-schema"></a><span data-ttu-id="a2f86-105">新しいスキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="a2f86-105">To create a new schema</span></span>  
  
1.  <span data-ttu-id="a2f86-106">**ソリューション エクスプ ローラー**, 、スキーマを追加する BizTalk プロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2f86-106">In **Solution Explorer**, select the BizTalk project to which you want to add a schema.</span></span>  
  
2.  <span data-ttu-id="a2f86-107">**[プロジェクト]** メニューの **[新しい項目の追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2f86-107">On the **Project** menu, click **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="a2f86-108">**新しい項目の追加 - \< *BizTalk ProjectName* \>**  ] ダイアログ ボックスで、**テンプレート**セクションで、[**スキーマ**.</span><span class="sxs-lookup"><span data-stu-id="a2f86-108">In the **Add New Item - \<*BizTalk ProjectName*\>** dialog box, in the **Templates** section, click **Schema**.</span></span>  
  
4.  <span data-ttu-id="a2f86-109">**名前** ボックスで、スキーマの名前を入力してクリックして **追加**します。</span><span class="sxs-lookup"><span data-stu-id="a2f86-109">In the **Name** box, type a name for the schema, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="a2f86-110">必要に応じて F4 キーを押し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="a2f86-110">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
6.  <span data-ttu-id="a2f86-111">スキーマ ツリー ビューで、選択、 **スキーマ** ノード、し、[プロパティ] ウィンドウで次のように選択します。、 **ターゲットの名前空間** プロパティとターゲットの名前空間の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a2f86-111">In the schema tree view, select the **Schema** node, and then in the Properties window, select the **Target Namespace** property and type a name for the target namespace.</span></span> <span data-ttu-id="a2f86-112">スキーマの作成の初期段階では、このプロパティを設定することが重要であります。既定値は使用しないでください **ターゲットの名前空間** プロパティの値。</span><span class="sxs-lookup"><span data-stu-id="a2f86-112">It is important that you set this property in this initial phase of schema creation; avoid using the default **Target Namespace** property value.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a2f86-113">プロジェクトのメンバー ファイル (スキーマ ファイルなど) に特定の名前を使用すると、C# の予約語や .NET Framework の型/名前空間名 (System など) との競合によってコンパイル エラーになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2f86-113">Certain name choices for project member files, such as schema files, can cause compilation errors later on due to conflicts with C# reserved words and.NET Framework type and namespace names (such as System).</span></span> <span data-ttu-id="a2f86-114">このようなスキーマ名には、schema.xsd、XmlContent、RootNodes などがあります。</span><span class="sxs-lookup"><span data-stu-id="a2f86-114">Examples for schemas include schema.xsd, XmlContent, and RootNodes.</span></span> <span data-ttu-id="a2f86-115">これは、 **型名** の基本 (拡張子を除いた部分のプロパティの既定値、  **ファイル名** プロパティです。</span><span class="sxs-lookup"><span data-stu-id="a2f86-115">This is because the **Type Name** property defaults to the base (non-extension) portion of the  **Filename** property.</span></span> <span data-ttu-id="a2f86-116">この種のコンパイル エラーを回避するには、明示的の値を変更して、 **型名** 競合しないやすいプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a2f86-116">You can work around this type of compilation error by explicitly changing the value of the **Type Name** property to something that does not conflict.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a2f86-117">必要に応じて、スキーマ内のレコードとフィールド、および、関連するプロパティを追加、削除、変更します。</span><span class="sxs-lookup"><span data-stu-id="a2f86-117">You may need to add, delete, and modify the records and fields in your schema along with their associated properties.</span></span> <span data-ttu-id="a2f86-118">詳細についてを参照してください。 [、スキーマ内のノードを管理する](../core/managing-the-nodes-within-a-schema.md)です。</span><span class="sxs-lookup"><span data-stu-id="a2f86-118">To learn more about this, see [Managing the Nodes Within a Schema](../core/managing-the-nodes-within-a-schema.md).</span></span>  
  
### <a name="to-generate-a-schema-from-a-non-xsd-source"></a><span data-ttu-id="a2f86-119">XSD 以外のソースからスキーマを生成するには</span><span class="sxs-lookup"><span data-stu-id="a2f86-119">To generate a schema from a non-XSD source</span></span>  
  
1.  <span data-ttu-id="a2f86-120">**ソリューション エクスプ ローラー**, 、BizTalk プロジェクトを右クリックし、順にポイント **追加**, 、クリックして **生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="a2f86-120">In **Solution Explorer**, right-click a BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="a2f86-121">**生成した項目の追加 - \< *BizTalk ProjectName* \>**  ] ダイアログ ボックスで、**テンプレート**セクションで、[**生成スキーマ**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="a2f86-121">In the **Add Generated Items - \<*BizTalk ProjectName*\>** dialog box, in the **Templates** section, click **Generate Schemas**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="a2f86-122">**スキーマの生成** ダイアログ ボックスで、 **ドキュメントの種類** ドロップダウン リストで、 **XDR スキーマ**, 、**DTD スキーマ**, 、または **整形式 XML**します。</span><span class="sxs-lookup"><span data-stu-id="a2f86-122">In the **Generate Schemas** dialog box, in the **Document type** drop-down list, select **XDR Schema**, **DTD Schema**, or **Well-Formed XML**.</span></span>  
  
     <span data-ttu-id="a2f86-123">いずれかを表示する場合は **DTD (読み込まれていません)** または **整形式 XML (読み込まれていません)** ドロップダウン リストで、適切なドキュメントの種類を選択し、不足した DLL をインストールするプロセスをガイドします。</span><span class="sxs-lookup"><span data-stu-id="a2f86-123">If you see either **DTD (Not Loaded)** or **Well-Formed XML (Not Loaded)** in the drop-down list, select the appropriate document type anyway, and you will be guided through the process of installing the missing DLL.</span></span> <span data-ttu-id="a2f86-124">その後で、上記の手順を繰り返してください。</span><span class="sxs-lookup"><span data-stu-id="a2f86-124">Then repeat these steps.</span></span>  
  
4.  <span data-ttu-id="a2f86-125">**スキーマの生成** ダイアログ ボックスで、をクリックして **参照**, 、ファイルをインポートする をクリックして選択 **開いている**します。</span><span class="sxs-lookup"><span data-stu-id="a2f86-125">In the **Generate Schemas** dialog box, click **Browse**, locate the file you want to import, and then click **Open**.</span></span> <span data-ttu-id="a2f86-126">前の手順で選択したドキュメント型のファイルを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2f86-126">The file you locate must match the document type you selected in the previous step.</span></span>  
  
     <span data-ttu-id="a2f86-127">指定したファイルから新しいスキーマが生成され、BizTalk エディターに表示されます。スキーマ名には、指定したファイルと同じ名前 (拡張子は .xsd) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2f86-127">A new schema is generated from the specified file, using the same name as that file with the .xsd extension, and opened in BizTalk Editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f86-128">参照</span><span class="sxs-lookup"><span data-stu-id="a2f86-128">See Also</span></span>  
 [<span data-ttu-id="a2f86-129">プロジェクト内のスキーマの管理</span><span class="sxs-lookup"><span data-stu-id="a2f86-129">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)