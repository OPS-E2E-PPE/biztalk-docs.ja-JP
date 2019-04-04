---
title: カスタム コードを使用してオーケストレーションのデバッグ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, debugging
- building, debugging
ms.assetid: 94e569fa-8dea-4027-abb5-37b4a8015621
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e32358f48099b9d184a9ff1ff62a0a85af595b89
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995339"
---
# <a name="debugging-orchestrations-by-using-custom-code"></a><span data-ttu-id="80817-102">カスタム コードを使用したオーケストレーションのデバッグ</span><span class="sxs-lookup"><span data-stu-id="80817-102">Debugging Orchestrations by using Custom Code</span></span>
<span data-ttu-id="80817-103">オーケストレーションがテスト環境で使用するか、またはプロトタイプを作成し、メッセージ フィールドとオーケストレーション変数の値を変更するは、出力を書き込むことができます、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で次のコードを使用して、コンソール**式**図形。</span><span class="sxs-lookup"><span data-stu-id="80817-103">If your orchestration is going to be exercised in a test environment or you are creating a prototype and want to modify the values of message fields and orchestration variables, you can write the output to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] console by using the following code in an **Expression** shape:</span></span>  
  
```  
System.Diagnostics.Debug.WriteLine(iResult);  
```  
  
 <span data-ttu-id="80817-104">これを配置する必要がある**式**デバッグの結果を出力できるように、操作を実行する図形の直後後の図形。</span><span class="sxs-lookup"><span data-stu-id="80817-104">You need to place this **Expression** shape immediately after the shape that performs the operation so that you can output the result for debugging.</span></span>  
  
 <span data-ttu-id="80817-105">または、単純なを記述することができます、クラスを使用してデバッグ DLL を作成してカスタムのデバッガーには形式のメッセージがオーケストレーションで定義されているし、デバッグ DLL で参照されている入力として受け取るメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="80817-105">Alternatively, you can write a simple custom debugger by creating a debugging DLL with a class that includes a method which takes as input a message with a format defined in your orchestration and referenced in the debug DLL.</span></span> <span data-ttu-id="80817-106">メッセージをパラメーターとして渡すことの詳細については、[オブジェクトを作成してオブジェクトのメソッドを呼び出す式を使用する方法](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80817-106">For more information about passing a message as a parameter, see [How to Use Expressions to Create Objects and Call Object Methods](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md).</span></span>  
  
 <span data-ttu-id="80817-107">このメソッドでは、コンボ ボックスまたは他のコントロールを含むデバッグ用のダイアログを表示し、ユーザーに値の変更を許可することができます。その後、編集されたメッセージを取得し、それを戻り値として渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="80817-107">This method can bring up a debug dialog that includes a combo box or other control to allow user modification of values, puts the edited message back together, and passes it back out as the return value.</span></span>  
  
 <span data-ttu-id="80817-108">追加できるかどうか、オーケストレーションがデバッグ モードでは、その値を変更できるように、オーケストレーションで、ポイントがある任意の場所を示すブール値変数を設定、**判断**ライブのいずれかの図形実行、デバッグ モード変数が True に設定されている場合にのみ、または特定の条件を確認することが発生したときに分岐します。</span><span class="sxs-lookup"><span data-stu-id="80817-108">Set up a Boolean variable to indicate whether or not your orchestration is in debug mode, then wherever you have a point in your orchestration at which you would like to be able to modify values, you can add a **Decide** shape with one live branch that runs only when your debug mode variable is set to True, or when a particular condition arises that you want to examine.</span></span> <span data-ttu-id="80817-109">メソッドを呼び出す、**式**のライブ分岐内の図形、**判断**します。</span><span class="sxs-lookup"><span data-stu-id="80817-109">You call your method from an **Expression** shape in the live branch of the **Decide**.</span></span> <span data-ttu-id="80817-110">False に、デバッグ モード変数を設定または削除するデバッグが不要になったときに、**判断**なくなった完全再コンパイルしてください。</span><span class="sxs-lookup"><span data-stu-id="80817-110">When you no longer need to debug, you set your debug mode variable to False, or remove the **Decide** shape(s) altogether and recompile.</span></span>  
  
## <a name="to-debug-a-net-component-called-by-an-orchestration"></a><span data-ttu-id="80817-111">オーケストレーションから呼び出される .NET コンポーネントをデバッグするには</span><span class="sxs-lookup"><span data-stu-id="80817-111">To Debug a .NET component called by an Orchestration</span></span>  
 <span data-ttu-id="80817-112">オーケストレーションから呼び出される .NET コンポーネントをデバッグするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="80817-112">The following steps demonstrate how to debug a .NET component called by an Orchestration:</span></span>  
  
1. <span data-ttu-id="80817-113">コンポーネントの [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="80817-113">Open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for your component.</span></span>  
  
2. <span data-ttu-id="80817-114">コンポーネント内の、オーケストレーションから呼び出されるメソッドにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="80817-114">Set a breakpoint in your component on the method that is called by the orchestration.</span></span>  
  
3. <span data-ttu-id="80817-115">をクリックして、**デバッグ**メニュー選択し、**プロセスにアタッチしています.**</span><span class="sxs-lookup"><span data-stu-id="80817-115">Click the **Debug** menu and select **Attach to Process…**</span></span> <span data-ttu-id="80817-116">表示する、**プロセスにアタッチ**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="80817-116">to display the **Attach to Process** dialog.</span></span>  
  
4. <span data-ttu-id="80817-117">をクリックして、**を選択しています.**</span><span class="sxs-lookup"><span data-stu-id="80817-117">Click the **Select…**</span></span> <span data-ttu-id="80817-118">ボタンの横に、**にアタッチ:** を表示するテキスト ボックス、**コードの種類の選択**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="80817-118">button next to the **Attach to:** text box to display the **Select Code Type** dialog.</span></span>  
  
5. <span data-ttu-id="80817-119">オプションを選択する をクリックします**コードの種類:** 選択と**マネージ**順にクリックします、 **ok**ボタン。</span><span class="sxs-lookup"><span data-stu-id="80817-119">Click to select the option to **Debug these code types:** and select **Managed** and then click the **OK** button.</span></span>  
  
6. <span data-ttu-id="80817-120">クリックして選択し、 **BTSNTSvc.exe**からプロセス**選択可能なプロセス**順にクリックします、**アタッチ**ボタン。</span><span class="sxs-lookup"><span data-stu-id="80817-120">Click to select the **BTSNTSvc.exe** process from **Available Processes** and then click the **Attach** button.</span></span>  
  
7. <span data-ttu-id="80817-121">受信ポートを介してオーケストレーションにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="80817-121">Send a message to your orchestration through a receive port.</span></span>  
  
8. <span data-ttu-id="80817-122">.NET コンポーネント内のブレークポイントで実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="80817-122">The .NET component should be stopped in the breakpoint.</span></span>  
  
9. <span data-ttu-id="80817-123">通常どおり [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でデバッグ作業を行います。</span><span class="sxs-lookup"><span data-stu-id="80817-123">You can perform debugging as usual with [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="80817-124">最良の結果を得るには、.NET コンポーネントをグローバル アセンブリ キャッシュ (GAC) に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80817-124">For best results, the .NET component should be registered in the Global Assembly Cache (GAC).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80817-125">参照</span><span class="sxs-lookup"><span data-stu-id="80817-125">See Also</span></span>  
 <span data-ttu-id="80817-126">[オーケストレーション デバッガーのユーザー インターフェイス](../core/orchestration-debugger-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="80817-126">[Orchestration Debugger User Interface](../core/orchestration-debugger-user-interface.md) </span></span>  
 [<span data-ttu-id="80817-127">オーケストレーションのデバッグ</span><span class="sxs-lookup"><span data-stu-id="80817-127">Debugging Orchestrations</span></span>](../core/debugging-orchestrations.md)