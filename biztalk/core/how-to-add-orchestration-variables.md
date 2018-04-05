---
title: オーケストレーション変数を追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: c387cd56-5443-4de2-bbda-be34b95cbe71
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb8516ceb780e64c4f4a01370de0e7c40098f3da
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-add-orchestration-variables"></a><span data-ttu-id="9b190-102">オーケストレーション変数を追加する方法</span><span class="sxs-lookup"><span data-stu-id="9b190-102">How to Add Orchestration Variables</span></span>
<span data-ttu-id="9b190-103">オーケストレーションの種類 ウィンドウでは、オーケストレーションのプロパティを管理することができます (とも呼ばれる**サービス**プロパティ)、パラメーター、ポート、メッセージ、およびその他の変数です。</span><span class="sxs-lookup"><span data-stu-id="9b190-103">The Orchestration View window enables you to manage an orchestration's properties (also known as **Service** properties), parameters, ports, messages, and other variables.</span></span> <span data-ttu-id="9b190-104">ポートおよびメッセージに加えて、整数型の変数、ブール変数、文字列変数、または .NET クラスの変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9b190-104">In addition to ports and messages, you can create integer variables, Boolean variables, string variables, or variables of a .NET class.</span></span>  
  
 <span data-ttu-id="9b190-105">[オーケストレーションの種類] ウィンドウでは、スコープに属する変数も管理できます。</span><span class="sxs-lookup"><span data-stu-id="9b190-105">You can also use the Orchestration View window to manage the variables that belong to your scopes.</span></span>  
  
### <a name="to-add-a-variable"></a><span data-ttu-id="9b190-106">変数を追加するには</span><span class="sxs-lookup"><span data-stu-id="9b190-106">To add a variable</span></span>  
  
1.  <span data-ttu-id="9b190-107">オーケストレーションの種類 ウィンドウで右クリックし、**変数**フォルダーをクリックして**新しい変数**です。</span><span class="sxs-lookup"><span data-stu-id="9b190-107">In the Orchestration View window, right-click the **Variables** folder and then click **New Variable**.</span></span>  
  
     <span data-ttu-id="9b190-108">**変数**が折りたたまれている場合、フォルダーを展開し、新しい変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="9b190-108">The **Variables** folder expands, if collapsed, and a new variable is added.</span></span>  
  
2.  <span data-ttu-id="9b190-109">[プロパティ] ウィンドウの "識別子" プロパティに名前を入力して、変数の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b190-109">Name the variable by typing a name in the Identifier property in the Properties window.</span></span>  
  
3.  <span data-ttu-id="9b190-110">変数と .NET クラスなどの種類を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="9b190-110">Associate the variable with a type, such as a .NET class.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9b190-111">**型**ドロップダウン リストには、次の定義済み変数の型が含まれています:**ブール**、**バイト**、 **datetime**、 **10 進**、**二重**、 **int16**、 **int32**、 **int64**、 **sbyte**、**単一**、**文字列**、 **timespan**、 **uint16**、 **uint32**、および**uint64**です。</span><span class="sxs-lookup"><span data-stu-id="9b190-111">The **Types** drop-down list contains the following predefined variable types: **boolean**, **byte**, **datetime**, **decimal**, **double**, **int16**, **int32**, **int64**, **sbyte**, **single**, **string**, **timespan**, **uint16**, **uint32**, and **uint64**.</span></span> <span data-ttu-id="9b190-112">選択して、.NET データ型とクラスをアクセスすることも **\<.NET クラス.\>** 、これにより、**成果物の種類の選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9b190-112">You can also access .NET data types and classes by selecting **\<.NET Class...\>**, which brings up the **Select Artifact Type** dialog box.</span></span>  
  
4.  <span data-ttu-id="9b190-113">定義済みの変数の型を選択する場合、変数の初期値を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="9b190-113">If you select a predefined variable type, you have the option of specifying an initial value for the variable.</span></span> <span data-ttu-id="9b190-114">[プロパティ] ウィンドウで、設定、**初期値**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="9b190-114">In the Properties window, set the **Initial Value** property.</span></span>  
  
     <span data-ttu-id="9b190-115">初期値設定せず、選択された型が .NET クラスである場合、既定のコンストラクターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9b190-115">Otherwise, if the selected type is a .NET class, you have the option of using a default constructor.</span></span> <span data-ttu-id="9b190-116">[プロパティ] ウィンドウで、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="9b190-116">In the Properties window, set the following property:</span></span>  
  
    |<span data-ttu-id="9b190-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9b190-117">Property</span></span>|<span data-ttu-id="9b190-118">Description</span><span class="sxs-lookup"><span data-stu-id="9b190-118">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="9b190-119">**既定のコンス トラクターを使用します。**</span><span class="sxs-lookup"><span data-stu-id="9b190-119">**Use Default Constructor**</span></span>|<span data-ttu-id="9b190-120">.NET クラスで既定のコンストラクターが使用できる場合、このプロパティを使用して、初めて変数を使用するときに既定のコンストラクターが呼び出されるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9b190-120">If a default constructor is available for a .NET class, this property determines whether the default constructor will be called when you use the variable for the first time:</span></span><br /><br /> <span data-ttu-id="9b190-121">True: 既定のコンス トラクターが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9b190-121">True—The default constructor will be called.</span></span> <span data-ttu-id="9b190-122">これは、既定のコンストラクターが使用できる場合の既定値です。</span><span class="sxs-lookup"><span data-stu-id="9b190-122">This is the default value when a default constructor is available.</span></span><br /><br /> <span data-ttu-id="9b190-123">False-既定のコンス トラクターは呼び出されません。式でコンス トラクターを呼び出すか、オーケストレーションで使用する前に、変数への代入を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b190-123">False—The default constructor will not be called; you must call a constructor in an expression or make an assignment to the variable before you can use it in your orchestration.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="9b190-124">既定のコンス トラクターは、入力パラメーターを必要とする場合は、設定**既定コンス トラクターを使用**に**False**からコンス トラクターを呼び出すと、**割り当て**図形の例では、`myVariable = myNamespace.myClass (param1, param2)`です。</span><span class="sxs-lookup"><span data-stu-id="9b190-124">If the default constructor requires input parameters, you can set **Use Default Constructor** to **False** and then call the constructor from an **Assignment** shape; for example, `myVariable = myNamespace.myClass (param1, param2)`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9b190-125">変数をオーケストレーションに追加する場合、変数を完全に定義する前に、オーケストレーション内の感嘆符を確認します。</span><span class="sxs-lookup"><span data-stu-id="9b190-125">When you add a variable to the orchestration, before it is fully defined, you will see exclamation marks in the orchestration.</span></span> <span data-ttu-id="9b190-126">この変数を完全に定義する前に削除してもオーケストレーション内に感嘆符が表示されている場合は、オーケストレーション パラメーターを作成してから削除して、オーケストレーションからこれらの感嘆符を強制的に削除できます。</span><span class="sxs-lookup"><span data-stu-id="9b190-126">If you delete this variable before it is fully defined and the exclamation marks still appear in the orchestration, you can force the orchestration to remove these exclamation marks by creating and then deleting an orchestration parameter.</span></span>  
  
### <a name="to-remove-a-variable"></a><span data-ttu-id="9b190-127">変数を削除するには</span><span class="sxs-lookup"><span data-stu-id="9b190-127">To remove a variable</span></span>  
  
-   <span data-ttu-id="9b190-128">オーケストレーションの種類 ウィンドウで、削除して、をクリックする変数を右クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="9b190-128">In the Orchestration View window, right-click the variable you want to remove and then click **Delete**.</span></span>