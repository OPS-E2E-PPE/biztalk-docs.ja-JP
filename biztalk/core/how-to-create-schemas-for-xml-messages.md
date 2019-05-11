---
title: XML メッセージ用スキーマの作成方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0270293-fe23-42bd-b090-e877d5e9ce0b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 993d491dd6eda8f066598c98be0790813cc1e491
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338960"
---
# <a name="how-to-create-schemas-for-xml-messages"></a><span data-ttu-id="4bb64-102">XML メッセージ用スキーマの作成方法</span><span class="sxs-lookup"><span data-stu-id="4bb64-102">How to Create Schemas for XML Messages</span></span>
<span data-ttu-id="4bb64-103">BizTalk メッセージのスキーマを作成するためのいくつかの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="4bb64-103">There are several methods for creating BizTalk message schemas.</span></span> <span data-ttu-id="4bb64-104">このトピックでは、これらのメソッドのいくつかの手順が説明します。</span><span class="sxs-lookup"><span data-stu-id="4bb64-104">This topic provides step-by-step instructions for some of those methods.</span></span>  
  
### <a name="to-create-a-new-schema"></a><span data-ttu-id="4bb64-105">新しいスキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="4bb64-105">To create a new schema</span></span>  
  
1. <span data-ttu-id="4bb64-106">**ソリューション エクスプ ローラー**スキーマを追加する BizTalk プロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="4bb64-106">In **Solution Explorer**, select the BizTalk project to which you want to add a schema.</span></span>  
  
2. <span data-ttu-id="4bb64-107">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bb64-107">On the **Project** menu, click **Add New Item**.</span></span>  
  
3. <span data-ttu-id="4bb64-108">**新しい項目の追加 - \< *BizTalk ProjectName* \>**  ] ダイアログ ボックスで、**テンプレート**セクションで、[ **スキーマ**.</span><span class="sxs-lookup"><span data-stu-id="4bb64-108">In the **Add New Item - \<*BizTalk ProjectName*\>** dialog box, in the **Templates** section, click **Schema**.</span></span>  
  
4. <span data-ttu-id="4bb64-109">**名前**ボックスで、スキーマの名前を入力し、クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="4bb64-109">In the **Name** box, type a name for the schema, and then click **Add**.</span></span>  
  
5. <span data-ttu-id="4bb64-110">必要に応じて F4 キーを押し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="4bb64-110">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
6. <span data-ttu-id="4bb64-111">スキーマ ツリー ビューで、選択、**スキーマ**ノード、し、プロパティ ウィンドウで、、 **Target Namespace**プロパティとターゲットの名前空間の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4bb64-111">In the schema tree view, select the **Schema** node, and then in the Properties window, select the **Target Namespace** property and type a name for the target namespace.</span></span> <span data-ttu-id="4bb64-112">スキーマ作成; の初期段階では、このプロパティを設定することが重要します。既定値は使用しないでください**Target Namespace**プロパティの値。</span><span class="sxs-lookup"><span data-stu-id="4bb64-112">It is important that you set this property in this initial phase of schema creation; avoid using the default **Target Namespace** property value.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4bb64-113">特定の名前のスキーマ ファイルなどのプロジェクト メンバー ファイルなる競合によってコンパイル エラー c# 予約語で (System など) と.net Framework 型と名前空間名。</span><span class="sxs-lookup"><span data-stu-id="4bb64-113">Certain name choices for project member files, such as schema files, can cause compilation errors later on due to conflicts with C# reserved words and.NET Framework type and namespace names (such as System).</span></span> <span data-ttu-id="4bb64-114">スキーマの例には、schema.xsd、XmlContent、および Rootnode が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4bb64-114">Examples for schemas include schema.xsd, XmlContent, and RootNodes.</span></span> <span data-ttu-id="4bb64-115">これは、ため、**型名**プロパティの既定値の基本 (拡張機能) の部分、**ファイル名**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4bb64-115">This is because the **Type Name** property defaults to the base (non-extension) portion of the  **Filename** property.</span></span> <span data-ttu-id="4bb64-116">この種のコンパイル エラーを回避するには、値を明示的に変更することで、**型名**プロパティを競合しないようにします。</span><span class="sxs-lookup"><span data-stu-id="4bb64-116">You can work around this type of compilation error by explicitly changing the value of the **Type Name** property to something that does not conflict.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4bb64-117">追加、削除、およびその関連プロパティと共に、スキーマのフィールドとレコードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bb64-117">You may need to add, delete, and modify the records and fields in your schema along with their associated properties.</span></span> <span data-ttu-id="4bb64-118">これに関する詳細についてを参照してください。[スキーマ内のノードを管理する](../core/managing-the-nodes-within-a-schema.md)します。</span><span class="sxs-lookup"><span data-stu-id="4bb64-118">To learn more about this, see [Managing the Nodes Within a Schema](../core/managing-the-nodes-within-a-schema.md).</span></span>  
  
### <a name="to-generate-a-schema-from-a-non-xsd-source"></a><span data-ttu-id="4bb64-119">XSD 以外のソースからスキーマを生成するには</span><span class="sxs-lookup"><span data-stu-id="4bb64-119">To generate a schema from a non-XSD source</span></span>  
  
1.  <span data-ttu-id="4bb64-120">**ソリューション エクスプ ローラー**、BizTalk プロジェクトを右クリックし、 をポイント**追加**、 をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="4bb64-120">In **Solution Explorer**, right-click a BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="4bb64-121">**生成した項目の追加 - \< *BizTalk ProjectName* \>**   ダイアログ ボックスで、**テンプレート**セクションで、**生成スキーマ**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="4bb64-121">In the **Add Generated Items - \<*BizTalk ProjectName*\>** dialog box, in the **Templates** section, click **Generate Schemas**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="4bb64-122">**スキーマの生成** ダイアログ ボックスで、**ドキュメントの種類**ドロップダウン リストで、 **XDR スキーマ**、 **DTD スキーマ**、または**整形式 XML**します。</span><span class="sxs-lookup"><span data-stu-id="4bb64-122">In the **Generate Schemas** dialog box, in the **Document type** drop-down list, select **XDR Schema**, **DTD Schema**, or **Well-Formed XML**.</span></span>  
  
     <span data-ttu-id="4bb64-123">いずれかが表示される場合**DTD (読み込まれていません)** または**整形式の XML (読み込まれていません)** ボックスの一覧で、適切なドキュメントの種類を選択しをインストールするプロセスをガイドします、DLL がありません。</span><span class="sxs-lookup"><span data-stu-id="4bb64-123">If you see either **DTD (Not Loaded)** or **Well-Formed XML (Not Loaded)** in the drop-down list, select the appropriate document type anyway, and you will be guided through the process of installing the missing DLL.</span></span> <span data-ttu-id="4bb64-124">次の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4bb64-124">Then repeat these steps.</span></span>  
  
4.  <span data-ttu-id="4bb64-125">**スキーマの生成**ダイアログ ボックスで、をクリックして**参照**、クリックして、インポートするファイルを見つけます**オープン**。</span><span class="sxs-lookup"><span data-stu-id="4bb64-125">In the **Generate Schemas** dialog box, click **Browse**, locate the file you want to import, and then click **Open**.</span></span> <span data-ttu-id="4bb64-126">ファイルを指定は、前の手順で選択したドキュメントの種類と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bb64-126">The file you locate must match the document type you selected in the previous step.</span></span>  
  
     <span data-ttu-id="4bb64-127">新しいスキーマは、拡張子は .xsd とそのファイルと同じ名前を使用して、BizTalk エディターで開かれる、指定したファイルから生成されます。</span><span class="sxs-lookup"><span data-stu-id="4bb64-127">A new schema is generated from the specified file, using the same name as that file with the .xsd extension, and opened in BizTalk Editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bb64-128">参照</span><span class="sxs-lookup"><span data-stu-id="4bb64-128">See Also</span></span>  
 [<span data-ttu-id="4bb64-129">プロジェクト内のスキーマの管理</span><span class="sxs-lookup"><span data-stu-id="4bb64-129">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)