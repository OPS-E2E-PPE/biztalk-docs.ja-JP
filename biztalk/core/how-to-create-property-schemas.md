---
title: プロパティ スキーマを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24086dea-62b8-4ef6-8af8-eb4ab7c3c018
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fcab4ad4370fe68558fe1ca47de13f9a896c5a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339380"
---
# <a name="how-to-create-property-schemas"></a><span data-ttu-id="341ce-102">プロパティ スキーマを作成する方法</span><span class="sxs-lookup"><span data-stu-id="341ce-102">How to Create Property Schemas</span></span>
<span data-ttu-id="341ce-103">プロパティ フィールドとしてフィールドを昇格する場合は、まず、プロパティ スキーマを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="341ce-103">If you choose to promote fields as property fields, you will need to define a property schema first.</span></span> <span data-ttu-id="341ce-104">このプロパティ スキーマでは、プロパティ スキーマに関連付けられているスキーマで定義されるインスタンス メッセージ内のフィールドを昇格するフィールドの非構造化データのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="341ce-104">This property schema specifies an unstructured collection of fields into which you can promote fields from within an instance message defined by a schema associated with your property schema.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="341ce-105">新しいスキーマを作成する既存のプロパティ スキーマを編集してください。</span><span class="sxs-lookup"><span data-stu-id="341ce-105">Do not copy and edit an existing property schema to create a new schema.</span></span> <span data-ttu-id="341ce-106">プロパティ スキーマには、スキーマに固有の内部データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="341ce-106">The property schema contains schema-specific internal data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="341ce-107">識別フィールドを昇格するプロパティ スキーマを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="341ce-107">You do not need to create a property schema to promote distinguished fields.</span></span>  
  
### <a name="to-create-a-property-schema"></a><span data-ttu-id="341ce-108">プロパティ スキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="341ce-108">To create a property schema</span></span>  
  
1.  <span data-ttu-id="341ce-109">**ソリューション エクスプ ローラー**、BizTalk プロジェクトを右クリックし、 をポイント**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="341ce-109">In **Solution Explorer**, right-click a BizTalk project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="341ce-110">**新しい項目の追加**] ダイアログ ボックスで、**テンプレート**セクションで、[**プロパティ スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="341ce-110">In the **Add New Item** dialog box, in the **Templates** section, click **Property Schema**.</span></span>  
  
3.  <span data-ttu-id="341ce-111">**名前**ボックスで、スキーマの名前を入力し、クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="341ce-111">In the **Name** box, type a name for the schema, and then click **Add**.</span></span>  
  
     <span data-ttu-id="341ce-112">新しいプロパティ スキーマが開き、既に含まれています、**フィールド要素**Property1 という名前のノード。</span><span class="sxs-lookup"><span data-stu-id="341ce-112">The new property schema opens, and it already contains a **Field Element** node named Property1.</span></span>  
  
4.  <span data-ttu-id="341ce-113">スキーマ ツリー内を右クリックし**フィールド要素**ノード、をクリックして**の名前を変更**や、スキーマ内の最初のプロパティのわかりやすい名前を入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="341ce-113">In the schema tree, right-click that **Field Element** node, click **Rename**, type a descriptive name for the first property in the schema, and then press ENTER.</span></span>  
  
5.  <span data-ttu-id="341ce-114">設定、**データ型**に適切なその他の関連するプロパティと、**フィールド要素**プロパティ ウィンドウ内のノード。</span><span class="sxs-lookup"><span data-stu-id="341ce-114">Set the **Data Type** and other relevant properties, as appropriate, for the **Field Element** node in the Properties window.</span></span>  
  
6.  <span data-ttu-id="341ce-115">挿入する場合**フィールド要素**追加のプロパティのノードを右クリックし、\<スキーマ\>ノード、をクリックして**スキーマ ノードの挿入**、順にクリックします**子フィールド要素**、し、手順 4. と 5. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="341ce-115">If you want to insert **Field Element** nodes for additional properties, right-click the \<Schema\> node, click **Insert Schema Node**, and then click **Child Field Element**, and then repeat steps 4 and 5.</span></span> <span data-ttu-id="341ce-116">必要なセットを作成するために必要な操作を繰り返して**フィールド要素**インスタンス メッセージから値を昇格するノード。</span><span class="sxs-lookup"><span data-stu-id="341ce-116">Repeat as necessary to create the required set of **Field Element** nodes into which you intend to promote values from instance messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="341ce-117">参照</span><span class="sxs-lookup"><span data-stu-id="341ce-117">See Also</span></span>  
 [<span data-ttu-id="341ce-118">プロジェクト内のスキーマの管理</span><span class="sxs-lookup"><span data-stu-id="341ce-118">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)