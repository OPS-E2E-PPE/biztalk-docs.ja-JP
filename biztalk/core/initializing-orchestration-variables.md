---
title: オーケストレーション変数の初期化 |Microsoft ドキュメント
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
ms.openlocfilehash: a90fbc33343e3576d6199a0a97a7a57ca881f720
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256826"
---
# <a name="initializing-orchestration-variables"></a><span data-ttu-id="255ab-102">オーケストレーション変数の初期化</span><span class="sxs-lookup"><span data-stu-id="255ab-102">Initializing Orchestration Variables</span></span>
<span data-ttu-id="255ab-103">変数の値は、[プロパティ] ウィンドウで設定することによって初期化できます。</span><span class="sxs-lookup"><span data-stu-id="255ab-103">You can initialize the value of a variable by setting it in the Properties window.</span></span> <span data-ttu-id="255ab-104">たとえば、設定、**初期値**System.Int32 型の変数を初期化するために 32 です。</span><span class="sxs-lookup"><span data-stu-id="255ab-104">For example, you can set the **Initial Value** to 32 to initialize the variable of type System.Int32.</span></span> <span data-ttu-id="255ab-105">文字列型の値に初期値を追加するときは、プロパティ ウィンドウで初期値を引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="255ab-105">When adding an initial value to a variable of type string, you must enclose the initial value in quotation marks in the Properties window.</span></span> <span data-ttu-id="255ab-106">文字列に引用符を含める場合は円記号をエスケープ文字として使用し、文字列にリテラル円記号を含める場合は連続する円記号を使用します。</span><span class="sxs-lookup"><span data-stu-id="255ab-106">If you want the string to contain a quotation mark, use the backslash as an escape character, and use consecutive backslashes when you want a literal backslash in your string.</span></span> <span data-ttu-id="255ab-107">場合は、変数の値を指定しないと、変数は既定値を割り当てる、オーケストレーションのインスタンスを作成するとすぐにします。</span><span class="sxs-lookup"><span data-stu-id="255ab-107">If you do not specify a value for your variables, your variables will be assigned default values as soon as an instance of your orchestration is created.</span></span>  
  
 <span data-ttu-id="255ab-108">変数がクラスのインスタンスである場合は、コンストラクターを指定して初期化できます。</span><span class="sxs-lookup"><span data-stu-id="255ab-108">If the variable is an instance of a class, you can specify a constructor to initialize it.</span></span> <span data-ttu-id="255ab-109">既定では、**既定コンス トラクターを使用**プロパティに設定されている**True**場合、既定のコンス トラクターは使用できません。 したがって、既定のコンス トラクターが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="255ab-109">By default, the **Use Default Constructor** property is set to **True** if a default constructor is available; therefore, the default constructor will be called.</span></span> <span data-ttu-id="255ab-110">既定のコンス トラクターを使用する場合で改めて変数を初期化する必要はありません、**式**図形を 2 回、コンス トラクターの呼び出しを回避します。</span><span class="sxs-lookup"><span data-stu-id="255ab-110">If you only intend to use the default constructor, you do not need to initialize the variables again in the **Expression** shape to avoid calling the constructor twice.</span></span> <span data-ttu-id="255ab-111">場合、**既定のコンス トラクターを使用して**プロパティに設定されている**False**既定のコンス トラクターは呼び出されません以外の場合は、式でコンス トラクターを呼び出すまたは使用する前に、変数に割り当てを作成する必要がありますで、オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="255ab-111">If the **Use Default Constructor** property is set to **False**, the default constructor will not be called; you must call a constructor in an expression or make an assignment to the variable before you can use it in your orchestration.</span></span> <span data-ttu-id="255ab-112">さらに、コンス トラクターは、入力パラメーターを必要とする場合は、設定する必要あります**既定のコンス トラクターを使用**に**False**からコンス トラクターを呼び出すと、**式**図形の例では、`myVariable = myNamespace.myClass (param1, param2)`です。</span><span class="sxs-lookup"><span data-stu-id="255ab-112">Moreover, if the constructor requires input parameters, you must set **Use Default Constructor** to **False** and then call the constructor from an **Expression** shape; for example, `myVariable = myNamespace.myClass (param1, param2)`.</span></span>  
  
 <span data-ttu-id="255ab-113">変数を明示的に初期化する必要が唯一の状況は、オーケストレーションに複数のアクティブ化が含まれている受信で利用できるよう、**スコープ**、**並列アクション**、または**リッスン**図形です。</span><span class="sxs-lookup"><span data-stu-id="255ab-113">The only circumstance in which you are required to explicitly initialize your variables is when your orchestration contains more than one activate receive, as is possible in a **Scope**, **Parallel Actions**, or **Listen** shape.</span></span> <span data-ttu-id="255ab-114">この場合、自動初期化が無効になり、使用する必要があります、**式**図形、変数を初期化します。</span><span class="sxs-lookup"><span data-stu-id="255ab-114">In this case, automatic initialization is disabled, and you must use an **Expression** shape to initialize your variables.</span></span> <span data-ttu-id="255ab-115">配置する必要があります、**式**図形のそれぞれのアクティブ化されたら、および任意の変数には、オーケストレーションでアクセスする前にします。</span><span class="sxs-lookup"><span data-stu-id="255ab-115">You must place an **Expression** shape after each activation receive, and before any variable is accessed in the orchestration.</span></span>