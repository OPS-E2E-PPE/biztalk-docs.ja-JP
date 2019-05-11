---
title: オーケストレーション変数の初期化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: 770e4e55-1fb9-4b43-854c-63aec5a3c5ba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0012e4783f3d8b30c38935f8bb22db8809cb3fa0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332008"
---
# <a name="initializing-orchestration-variables"></a><span data-ttu-id="ebdc9-102">オーケストレーション変数の初期化</span><span class="sxs-lookup"><span data-stu-id="ebdc9-102">Initializing Orchestration Variables</span></span>
<span data-ttu-id="ebdc9-103">[プロパティ] ウィンドウで設定することで、変数の値を初期化できます。</span><span class="sxs-lookup"><span data-stu-id="ebdc9-103">You can initialize the value of a variable by setting it in the Properties window.</span></span> <span data-ttu-id="ebdc9-104">たとえば、設定、**初期値**System.Int32 型の変数を初期化するために 32。</span><span class="sxs-lookup"><span data-stu-id="ebdc9-104">For example, you can set the **Initial Value** to 32 to initialize the variable of type System.Int32.</span></span> <span data-ttu-id="ebdc9-105">初期値を文字列型の変数を追加する場合は、[プロパティ] ウィンドウで、引用符で初期値を囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebdc9-105">When adding an initial value to a variable of type string, you must enclose the initial value in quotation marks in the Properties window.</span></span> <span data-ttu-id="ebdc9-106">文字列に引用符を含める場合は、バック スラッシュをエスケープ文字として使用し、文字列にリテラル円記号をする場合は、連続する円記号を使用します。</span><span class="sxs-lookup"><span data-stu-id="ebdc9-106">If you want the string to contain a quotation mark, use the backslash as an escape character, and use consecutive backslashes when you want a literal backslash in your string.</span></span> <span data-ttu-id="ebdc9-107">変数の値を指定しない場合、変数は既定値を割り当てる、オーケストレーションのインスタンスを作成するとすぐにします。</span><span class="sxs-lookup"><span data-stu-id="ebdc9-107">If you do not specify a value for your variables, your variables will be assigned default values as soon as an instance of your orchestration is created.</span></span>  
  
 <span data-ttu-id="ebdc9-108">変数がクラスのインスタンスの場合は、初期化するコンス トラクターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ebdc9-108">If the variable is an instance of a class, you can specify a constructor to initialize it.</span></span> <span data-ttu-id="ebdc9-109">既定で、**既定コンス トラクターを使用**プロパティに設定されて**True**既定のコンス トラクターは使用できません。 そのため、既定のコンス トラクターが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ebdc9-109">By default, the **Use Default Constructor** property is set to **True** if a default constructor is available; therefore, the default constructor will be called.</span></span> <span data-ttu-id="ebdc9-110">既定のコンス トラクターを使用する場合は、もう一度で変数を初期化する必要はありません、**式**コンス トラクターを 2 回呼び出すことを回避するために図形。</span><span class="sxs-lookup"><span data-stu-id="ebdc9-110">If you only intend to use the default constructor, you do not need to initialize the variables again in the **Expression** shape to avoid calling the constructor twice.</span></span> <span data-ttu-id="ebdc9-111">場合、**既定のコンス トラクターを使用して**プロパティに設定されて**False**既定のコンス トラクターは呼び出されません式でコンス トラクターを呼び出すか、使用する前に、変数への代入を行う必要があります。で、オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="ebdc9-111">If the **Use Default Constructor** property is set to **False**, the default constructor will not be called; you must call a constructor in an expression or make an assignment to the variable before you can use it in your orchestration.</span></span> <span data-ttu-id="ebdc9-112">さらに、コンス トラクターが入力パラメーターを必要とする必要があります設定する**既定のコンス トラクターを使用**に**False**をからコンス トラクターを呼び出して、**式**; 図形の例では、`myVariable = myNamespace.myClass (param1, param2)`します。</span><span class="sxs-lookup"><span data-stu-id="ebdc9-112">Moreover, if the constructor requires input parameters, you must set **Use Default Constructor** to **False** and then call the constructor from an **Expression** shape; for example, `myVariable = myNamespace.myClass (param1, param2)`.</span></span>  
  
 <span data-ttu-id="ebdc9-113">明示的に変数を初期化するために必要な唯一の状況は、オーケストレーションが含まれている複数のアクティブ化受信で可能な限り、**スコープ**、**並列アクション**、または**リッスン**図形。</span><span class="sxs-lookup"><span data-stu-id="ebdc9-113">The only circumstance in which you are required to explicitly initialize your variables is when your orchestration contains more than one activate receive, as is possible in a **Scope**, **Parallel Actions**, or **Listen** shape.</span></span> <span data-ttu-id="ebdc9-114">この場合、自動初期化を無効にし、使用する必要があります、**式**図形を変数を初期化します。</span><span class="sxs-lookup"><span data-stu-id="ebdc9-114">In this case, automatic initialization is disabled, and you must use an **Expression** shape to initialize your variables.</span></span> <span data-ttu-id="ebdc9-115">配置する必要があります、**式**図形の各アクティブ化受信、および任意の変数には、オーケストレーションでアクセスする前にします。</span><span class="sxs-lookup"><span data-stu-id="ebdc9-115">You must place an **Expression** shape after each activation receive, and before any variable is accessed in the orchestration.</span></span>