---
title: 構成情報 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], planning
- Call Rules shape [Orchestration Designer], configuring
ms.assetid: aa4924c6-4270-473b-aa0a-6d8b18375a39
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9a35767815eaf7406a7baae5d9dccb833492287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233466"
---
# <a name="configuration-information"></a><span data-ttu-id="4c473-102">構成情報</span><span class="sxs-lookup"><span data-stu-id="4c473-102">Configuration Information</span></span>
<span data-ttu-id="4c473-103">このトピックの内容を構成する方法を説明します、**ルールの呼び出し**図形です。</span><span class="sxs-lookup"><span data-stu-id="4c473-103">This topic describes how to configure the **Call Rules** shape.</span></span>  
  
## <a name="orchestration-variables-and-fact-types"></a><span data-ttu-id="4c473-104">オーケストレーションの変数とファクトの種類</span><span class="sxs-lookup"><span data-stu-id="4c473-104">Orchestration variables and fact types</span></span>  
 <span data-ttu-id="4c473-105">オーケストレーション内で、**ルールの呼び出し**図形が存在する、ポリシーで使用される型と一致する変数をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c473-105">In the orchestration where the **Call Rules** shape resides, you must have variables that match types used in the policy.</span></span> <span data-ttu-id="4c473-106">正しい型の変数がない場合、ポリシーに対して適切なパラメーターを提供できません。</span><span class="sxs-lookup"><span data-stu-id="4c473-106">If you do not have the correct types of variables, you cannot supply the correct parameters to the policy.</span></span> <span data-ttu-id="4c473-107">あると仮定する**ルールの呼び出し**図形をオーケストレーションや CallMyRules、CallMyRules を使用して MyPolicy を呼び出す。</span><span class="sxs-lookup"><span data-stu-id="4c473-107">Suppose that you have a **Call Rules** shape in an orchestration, CallMyRules, and you use CallMyRules to call MyPolicy.</span></span> <span data-ttu-id="4c473-108">MyPolicy に .NET クラス MyClass が使用されている場合、オーケストレーションにも MyAssembly.MyClass 型の変数を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c473-108">If a .NET class, MyClass, is used in MyPolicy, you must create a variable of a MyAssembly.MyClass type in the orchestration.</span></span> <span data-ttu-id="4c473-109">同様に、MyPolicy に**DataConnection**バインドの変数を作成する必要があります、 **Microsoft.RuleEngine.DataConnection**オーケストレーション内の型。</span><span class="sxs-lookup"><span data-stu-id="4c473-109">Similarly, if MyPolicy has **DataConnection** bindings, you must create a variable of a **Microsoft.RuleEngine.DataConnection** type in the orchestration.</span></span>  
  
 <span data-ttu-id="4c473-110">オーケストレーションに変数を作成し、さらに、これらの変数のインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c473-110">In addition to creating the variables in the orchestration, you must also create instances for these variables.</span></span> <span data-ttu-id="4c473-111">追加することでこれを行う、**式**図形をオーケストレーションにします。</span><span class="sxs-lookup"><span data-stu-id="4c473-111">You can do this by adding an **Expression** shape to your orchestration.</span></span> <span data-ttu-id="4c473-112">前の例を使用して、インスタンスを作成、MyAssembly.MyClass のインスタンスと**DataConnection**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="4c473-112">Using the preceding example, you should instantiate a MyAssembly.MyClass instance and a **DataConnection** instance.</span></span> <span data-ttu-id="4c473-113">インスタンスを作成する、 **DataConnection**インスタンス、以下を実行できます。</span><span class="sxs-lookup"><span data-stu-id="4c473-113">To instantiate the **DataConnection** instance, you do the following:</span></span>  
  
-   <span data-ttu-id="4c473-114">作成、 **SqlConnection**インスタンスし、して MySqlCon に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4c473-114">Create a **SqlConnection** instance and assign it to MySqlCon.</span></span>  
  
-   <span data-ttu-id="4c473-115">作成、 **DataConnection**をインスタンス化し、dataConnection に割り当てます (の変数**DataConnection**型)、次のコード フラグメントで示すように。</span><span class="sxs-lookup"><span data-stu-id="4c473-115">Create a **DataConnection** instance and assign it to dataConnection (variable of **DataConnection** type), as shown in the following code fragment:</span></span>  
  
    ```  
    dataConnection = new Microsoft.RuleEngine.DataConnection("NameOfSqlDatabaseHere", "NameOfYourTableHere", MySqlCon);  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="4c473-116">ファクトの種類と一致する変数があるない場合、これらの型は、パラメーターとしてでは表示されません、**ポリシー パラメーターの指定**リスト ボックスで、 **CallRules ポリシーの構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4c473-116">If you do not have variables matching the fact types, these types will not appear as parameters in the **Specify policy parameters** list box in the **CallRules policy configuration** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c473-117">オーケストレーション エンジンは、BRE ポリシーへのパラメーターとして指定したメッセージ変数を自動的に変換**TypedXmlDocument**オブジェクト、およびポリシーを実行する前に、ルール エンジンの作業メモリにアサートします。</span><span class="sxs-lookup"><span data-stu-id="4c473-117">The orchestration engine automatically converts the message variables you specify as parameters to a BRE policy into **TypedXmlDocument** objects, and asserts them into working memory of the rule engine prior to executing the policy.</span></span> <span data-ttu-id="4c473-118">このため、.NET やデータベース ファクトの場合とは異なり、TypedXmlDocument 型の変数を宣言する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4c473-118">Therefore, you do not need to declare variables of type TypedXmlDocument as you did for .NET and database facts.</span></span>  
  
## <a name="message-type-and-document-type"></a><span data-ttu-id="4c473-119">メッセージの種類とドキュメントの種類</span><span class="sxs-lookup"><span data-stu-id="4c473-119">Message type and document type</span></span>  
 <span data-ttu-id="4c473-120">確認する必要があります、 **DocumentType** (つまり、ビジネス ルール作成ツールで実装すると)、ビジネス ルールで使用される XML ノードのプロパティと同じ、 **MessageType**で定義されている XML ノード、オーケストレーション: と一致している必要があります、 **MessageType**メッセージまたはでルール エンジンに渡されるメッセージ部分の**ルールの呼び出し**図形です。</span><span class="sxs-lookup"><span data-stu-id="4c473-120">You must ensure that the **DocumentType** property for XML nodes used in your business rule (that you implement in the Business Rule Composer) is the same as the **MessageType** for those XML nodes defined in the orchestration—it must match the **MessageType** of the message or message part that will be passed to the rule engine in the **Call Rules** shape.</span></span>  
  
 <span data-ttu-id="4c473-121">たとえば、BizTalk プロジェクトで、注文書 (PO) XML スキーマを定義する場合、 **MessageType**このスキーマに定義された**BTSProject.PO** (場合**BTSProject**は、名前空間または既定の名前空間を使用して、プロジェクト名)。</span><span class="sxs-lookup"><span data-stu-id="4c473-121">For example, if you define a purchase order (PO) XML schema in a BizTalk project, the **MessageType** defined for this schema is **BTSProject.PO** (if **BTSProject** is the namespace or the project name using the default namespace).</span></span>  
  
 <span data-ttu-id="4c473-122">場合、 **\amount**要素、ルールの定義を削除する前にする必要がありますを変更するその**DocumentType**プロパティを**BTSProject.PO**プロパティ ウィンドウ.</span><span class="sxs-lookup"><span data-stu-id="4c473-122">In the case of the **PO\Amount** element, before you drop it into a rule definition, you must change its **DocumentType**property to **BTSProject.PO** in the properties window.</span></span> <span data-ttu-id="4c473-123">プロパティ ウィンドウをアクセスするには、スキーマ内の任意のノードを選択すると、 **XML スキーマ** タブで、ファクト エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="4c473-123">You can access the properties window when any node in the schema is selected on the **XML Schemas** tab in the Facts Explorer.</span></span> <span data-ttu-id="4c473-124">このスキーマはスキーマ内のすべての要素に適用されますが、永続化されません。</span><span class="sxs-lookup"><span data-stu-id="4c473-124">This change is applied for all elements in the schema, but is not persisted with the schema.</span></span> <span data-ttu-id="4c473-125">ビジネス ルール作成ツールを起動したり、スキーマを再度読み込んだときに、スキーマを再設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c473-125">It must be reset when the Business Rule Composer is launched or the schema is reloaded.</span></span> <span data-ttu-id="4c473-126">これは、XML スキーマまたは XML スキーマから直接構築されたルールに基づいてボキャブラリを定義する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="4c473-126">This is required for vocabulary definitions based either on XML schemas or on rules built directly from XML schemas.</span></span> <span data-ttu-id="4c473-127">これを行わない場合、ポリシーを実行できますが、**ルールの呼び出し**図形が正しく機能しないと、メッセージの種類に表示されません、**ポリシー パラメーターの指定**リスト ボックスで、 **[CallRules ポリシーの構成**] ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4c473-127">If you do not do this, you can still execute the policy, but the **Call Rules** shape will not work correctly, and message type will not appear in the **Specify policy parameters** list box in the **CallRules policy configuration** dialog box.</span></span>