---
title: "プロパティ スキーマを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24086dea-62b8-4ef6-8af8-eb4ab7c3c018
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee97f4cb3065fdb201ec19f88a79e7899f03ac49
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-create-property-schemas"></a><span data-ttu-id="323c3-102">プロパティ スキーマを作成する方法</span><span class="sxs-lookup"><span data-stu-id="323c3-102">How to Create Property Schemas</span></span>
<span data-ttu-id="323c3-103">プロパティ フィールドとしてフィールドを昇格する場合、最初にプロパティ スキーマを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="323c3-103">If you choose to promote fields as property fields, you will need to define a property schema first.</span></span> <span data-ttu-id="323c3-104">このプロパティ スキーマでは、構造化されていないフィールドの集合を指定します。プロパティ スキーマに関連するスキーマで定義されるインスタンス メッセージから、構造化されていないフィールドの集合にフィールドを昇格できます。</span><span class="sxs-lookup"><span data-stu-id="323c3-104">This property schema specifies an unstructured collection of fields into which you can promote fields from within an instance message defined by a schema associated with your property schema.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="323c3-105">新しいスキーマを作成する場合は、既存のプロパティ スキーマのコピーや編集はしないでください。</span><span class="sxs-lookup"><span data-stu-id="323c3-105">Do not copy and edit an existing property schema to create a new schema.</span></span> <span data-ttu-id="323c3-106">プロパティ スキーマには、スキーマ固有の内部データが含まれるためです。</span><span class="sxs-lookup"><span data-stu-id="323c3-106">The property schema contains schema-specific internal data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="323c3-107">識別フィールドの昇格にプロパティ スキーマを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="323c3-107">You do not need to create a property schema to promote distinguished fields.</span></span>  
  
### <a name="to-create-a-property-schema"></a><span data-ttu-id="323c3-108">プロパティ スキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="323c3-108">To create a property schema</span></span>  
  
1.  <span data-ttu-id="323c3-109">**ソリューション エクスプ ローラー**BizTalk プロジェクトを右クリックしをポイントし、**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="323c3-109">In **Solution Explorer**, right-click a BizTalk project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="323c3-110">**新しい項目の追加**] ダイアログ ボックスで、**テンプレート**セクションで、[**プロパティ スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="323c3-110">In the **Add New Item** dialog box, in the **Templates** section, click **Property Schema**.</span></span>  
  
3.  <span data-ttu-id="323c3-111">**名前**ボックスで、スキーマの名前を入力し、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="323c3-111">In the **Name** box, type a name for the schema, and then click **Add**.</span></span>  
  
     <span data-ttu-id="323c3-112">新しいプロパティ スキーマが開き、既に含まれています、**フィールド要素**Property1 という名前のノードです。</span><span class="sxs-lookup"><span data-stu-id="323c3-112">The new property schema opens, and it already contains a **Field Element** node named Property1.</span></span>  
  
4.  <span data-ttu-id="323c3-113">スキーマ ツリー内を右クリックし**フィールド要素** ノードをクリックして**の名前を変更**スキーマでは、最初のプロパティのわかりやすい名前を入力して、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="323c3-113">In the schema tree, right-click that **Field Element** node, click **Rename**, type a descriptive name for the first property in the schema, and then press ENTER.</span></span>  
  
5.  <span data-ttu-id="323c3-114">設定、**データ型**およびに応じて、他の関連するプロパティ、**フィールド要素**プロパティ ウィンドウ内のノードです。</span><span class="sxs-lookup"><span data-stu-id="323c3-114">Set the **Data Type** and other relevant properties, as appropriate, for the **Field Element** node in the Properties window.</span></span>  
  
6.  <span data-ttu-id="323c3-115">挿入する場合**フィールド要素**追加のプロパティのノードを右クリックし、\<スキーマ\>ノード、をクリックして**スキーマ ノードの挿入**、クリックして**子フィールド要素**、手順 4. と 5. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="323c3-115">If you want to insert **Field Element** nodes for additional properties, right-click the \<Schema\> node, click **Insert Schema Node**, and then click **Child Field Element**, and then repeat steps 4 and 5.</span></span> <span data-ttu-id="323c3-116">必要なセットを作成するために必要に応じて繰り返します**フィールド要素**インスタンス メッセージから値を昇格するノードです。</span><span class="sxs-lookup"><span data-stu-id="323c3-116">Repeat as necessary to create the required set of **Field Element** nodes into which you intend to promote values from instance messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="323c3-117">参照</span><span class="sxs-lookup"><span data-stu-id="323c3-117">See Also</span></span>  
 [<span data-ttu-id="323c3-118">プロジェクト内のスキーマの管理</span><span class="sxs-lookup"><span data-stu-id="323c3-118">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)