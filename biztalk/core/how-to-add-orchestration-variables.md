---
title: オーケストレーション変数を追加する方法 |Microsoft Docs
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
ms.openlocfilehash: 876799a7baf58d7dacc8185d09d6f9d63a70127d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343253"
---
# <a name="how-to-add-orchestration-variables"></a><span data-ttu-id="fdcf8-102">オーケストレーション変数を追加する方法</span><span class="sxs-lookup"><span data-stu-id="fdcf8-102">How to Add Orchestration Variables</span></span>
<span data-ttu-id="fdcf8-103">オーケストレーションの種類 ウィンドウでは、オーケストレーションのプロパティを管理することができます (とも呼ばれます**サービス**プロパティ)、パラメーター、ポート、メッセージ、およびその他の変数。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-103">The Orchestration View window enables you to manage an orchestration's properties (also known as **Service** properties), parameters, ports, messages, and other variables.</span></span> <span data-ttu-id="fdcf8-104">ポートとメッセージ、だけでなく、整数変数、ブール変数、文字列変数、または .NET クラスの変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-104">In addition to ports and messages, you can create integer variables, Boolean variables, string variables, or variables of a .NET class.</span></span>  
  
 <span data-ttu-id="fdcf8-105">スコープに属する変数を管理するのにオーケストレーションの種類 ウィンドウを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-105">You can also use the Orchestration View window to manage the variables that belong to your scopes.</span></span>  
  
### <a name="to-add-a-variable"></a><span data-ttu-id="fdcf8-106">変数を追加するには</span><span class="sxs-lookup"><span data-stu-id="fdcf8-106">To add a variable</span></span>  
  
1.  <span data-ttu-id="fdcf8-107">オーケストレーションの種類 ウィンドウで右クリックし、**変数**フォルダーをクリック**新しい変数**します。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-107">In the Orchestration View window, right-click the **Variables** folder and then click **New Variable**.</span></span>  
  
     <span data-ttu-id="fdcf8-108">**変数**が折りたたまれている場合、フォルダーを展開し、新しい変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-108">The **Variables** folder expands, if collapsed, and a new variable is added.</span></span>  
  
2.  <span data-ttu-id="fdcf8-109">[プロパティ] ウィンドウで、Identifier プロパティの名前を入力して変数を名前します。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-109">Name the variable by typing a name in the Identifier property in the Properties window.</span></span>  
  
3.  <span data-ttu-id="fdcf8-110">.NET クラスなどの型の変数を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-110">Associate the variable with a type, such as a .NET class.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fdcf8-111">**型**ドロップダウン リストには、次の定義済み変数の型が含まれています:**ブール**、**バイト**、 **datetime**、 **10 進**、**二重**、 **int16**、 **int32**、 **int64**、 **sbyte**、**単一**、**文字列**、 **timespan**、 **uint16**、 **uint32**、および**uint64**します。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-111">The **Types** drop-down list contains the following predefined variable types: **boolean**, **byte**, **datetime**, **decimal**, **double**, **int16**, **int32**, **int64**, **sbyte**, **single**, **string**, **timespan**, **uint16**, **uint32**, and **uint64**.</span></span> <span data-ttu-id="fdcf8-112">選択して、.NET データ型とクラスをアクセスすることができますも **\<.NET クラス.\>** が表示されます、**成果物の種類の選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-112">You can also access .NET data types and classes by selecting **\<.NET Class...\>**, which brings up the **Select Artifact Type** dialog box.</span></span>  
  
4.  <span data-ttu-id="fdcf8-113">定義済み変数の型を選択した場合、変数の初期値を指定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-113">If you select a predefined variable type, you have the option of specifying an initial value for the variable.</span></span> <span data-ttu-id="fdcf8-114">[プロパティ] ウィンドウで次のように設定します。、**初期値**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-114">In the Properties window, set the **Initial Value** property.</span></span>  
  
     <span data-ttu-id="fdcf8-115">それ以外の場合、選択した型が .NET クラスの場合は、既定のコンス トラクターを使用するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-115">Otherwise, if the selected type is a .NET class, you have the option of using a default constructor.</span></span> <span data-ttu-id="fdcf8-116">[プロパティ] ウィンドウでは、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-116">In the Properties window, set the following property:</span></span>  
  
    |<span data-ttu-id="fdcf8-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="fdcf8-117">Property</span></span>|<span data-ttu-id="fdcf8-118">説明</span><span class="sxs-lookup"><span data-stu-id="fdcf8-118">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="fdcf8-119">**既定のコンス トラクターを使用して、**</span><span class="sxs-lookup"><span data-stu-id="fdcf8-119">**Use Default Constructor**</span></span>|<span data-ttu-id="fdcf8-120">.NET クラスの既定のコンス トラクターがある場合、このプロパティは、最初に変数を使用するときに既定のコンス トラクターが呼び出されるかどうか決定します。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-120">If a default constructor is available for a .NET class, this property determines whether the default constructor will be called when you use the variable for the first time:</span></span><br /><br /> <span data-ttu-id="fdcf8-121">True-既定のコンス トラクターが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-121">True—The default constructor will be called.</span></span> <span data-ttu-id="fdcf8-122">これは、既定のコンス トラクターが使用可能な場合の既定値です。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-122">This is the default value when a default constructor is available.</span></span><br /><br /> <span data-ttu-id="fdcf8-123">False: 既定のコンス トラクターは呼び出されません。式でコンス トラクターを呼び出すか、オーケストレーションで使用する前に、変数への代入を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-123">False—The default constructor will not be called; you must call a constructor in an expression or make an assignment to the variable before you can use it in your orchestration.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="fdcf8-124">既定のコンス トラクターは、入力パラメーターを必要とする場合は設定できます**既定コンス トラクターを使用**に**False**をからコンス トラクターを呼び出して、**割り当て**; 図形の例では、`myVariable = myNamespace.myClass (param1, param2)`します。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-124">If the default constructor requires input parameters, you can set **Use Default Constructor** to **False** and then call the constructor from an **Assignment** shape; for example, `myVariable = myNamespace.myClass (param1, param2)`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fdcf8-125">完全に定義する前に、オーケストレーションに変数を追加するときに、オーケストレーション内の感嘆符が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-125">When you add a variable to the orchestration, before it is fully defined, you will see exclamation marks in the orchestration.</span></span> <span data-ttu-id="fdcf8-126">完全に定義して、感嘆符は、オーケストレーションが表示前に、この変数を削除する場合は、作成して、オーケストレーションのパラメーターを削除し、これらの感嘆符を削除するオーケストレーションを強制できます。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-126">If you delete this variable before it is fully defined and the exclamation marks still appear in the orchestration, you can force the orchestration to remove these exclamation marks by creating and then deleting an orchestration parameter.</span></span>  
  
### <a name="to-remove-a-variable"></a><span data-ttu-id="fdcf8-127">変数を削除するには</span><span class="sxs-lookup"><span data-stu-id="fdcf8-127">To remove a variable</span></span>  
  
-   <span data-ttu-id="fdcf8-128">オーケストレーションの種類 ウィンドウで、クリックして削除する変数を右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="fdcf8-128">In the Orchestration View window, right-click the variable you want to remove and then click **Delete**.</span></span>