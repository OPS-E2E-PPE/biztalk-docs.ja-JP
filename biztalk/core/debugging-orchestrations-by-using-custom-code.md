---
title: カスタム コードを使用してオーケストレーションのデバッグ |Microsoft ドキュメント
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
ms.openlocfilehash: 47f69fa635a90db90c461f75c300334ccc499b94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239890"
---
# <a name="debugging-orchestrations-by-using-custom-code"></a><span data-ttu-id="03998-102">カスタム コードを使用したオーケストレーションのデバッグ</span><span class="sxs-lookup"><span data-stu-id="03998-102">Debugging Orchestrations by using Custom Code</span></span>
<span data-ttu-id="03998-103">出力を書き込むことができる場合、オーケストレーションは、テスト環境で動作にプロトタイプを作成し、メッセージ フィールドとオーケストレーション変数の値を変更する、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で次のコードを使用して、コンソール**式**図形。</span><span class="sxs-lookup"><span data-stu-id="03998-103">If your orchestration is going to be exercised in a test environment or you are creating a prototype and want to modify the values of message fields and orchestration variables, you can write the output to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] console by using the following code in an **Expression** shape:</span></span>  
  
```  
System.Diagnostics.Debug.WriteLine(iResult);  
```  
  
 <span data-ttu-id="03998-104">このセクションを配置する必要があります**式**デバッグ結果を出力できるように、操作を実行する図形のすぐ後の図形です。</span><span class="sxs-lookup"><span data-stu-id="03998-104">You need to place this **Expression** shape immediately after the shape that performs the operation so that you can output the result for debugging.</span></span>  
  
 <span data-ttu-id="03998-105">または、単純なを記述する、クラスを含むデバッグ DLL を作成してカスタムのデバッガーには入力形式でメッセージが、オーケストレーションで定義されているし、デバッグ DLL 内で参照として使用するメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="03998-105">Alternatively, you can write a simple custom debugger by creating a debugging DLL with a class that includes a method which takes as input a message with a format defined in your orchestration and referenced in the debug DLL.</span></span> <span data-ttu-id="03998-106">詳細については、メッセージをパラメーターとして渡すを参照してください。[オブジェクトを作成するとオブジェクト メソッドの呼び出しに表現を使用する方法](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md)です。</span><span class="sxs-lookup"><span data-stu-id="03998-106">For more information about passing a message as a parameter, see [How to Use Expressions to Create Objects and Call Object Methods](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md).</span></span>  
  
 <span data-ttu-id="03998-107">このメソッドでは、コンボ ボックスまたは他のコントロールを含むデバッグ用のダイアログを表示し、ユーザーに値の変更を許可することができます。その後、編集されたメッセージを取得し、それを戻り値として渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="03998-107">This method can bring up a debug dialog that includes a combo box or other control to allow user modification of values, puts the edited message back together, and passes it back out as the return value.</span></span>  
  
 <span data-ttu-id="03998-108">ブール値変数を設定するかどうか、オーケストレーション デバッグ モードをするには値を変更できるように、オーケストレーションで、ポイントがある任意の場所を示す、ことができますを追加する、**判断**ライブのいずれかの図形分岐を確認する場合に、特定の条件が発生した場合、デバッグ モード変数が True に設定されている場合にのみまたはを実行します。</span><span class="sxs-lookup"><span data-stu-id="03998-108">Set up a Boolean variable to indicate whether or not your orchestration is in debug mode, then wherever you have a point in your orchestration at which you would like to be able to modify values, you can add a **Decide** shape with one live branch that runs only when your debug mode variable is set to True, or when a particular condition arises that you want to examine.</span></span> <span data-ttu-id="03998-109">メソッドの呼び出し、**式**のライブ分岐内の図形、**判断**です。</span><span class="sxs-lookup"><span data-stu-id="03998-109">You call your method from an **Expression** shape in the live branch of the **Decide**.</span></span> <span data-ttu-id="03998-110">デバッグ モード変数を False に設定または削除するデバッグが不要になったときに、**判断**図形を完全再コンパイルしてください。</span><span class="sxs-lookup"><span data-stu-id="03998-110">When you no longer need to debug, you set your debug mode variable to False, or remove the **Decide** shape(s) altogether and recompile.</span></span>  
  
## <a name="to-debug-a-net-component-called-by-an-orchestration"></a><span data-ttu-id="03998-111">オーケストレーションから呼び出される .NET コンポーネントをデバッグするには</span><span class="sxs-lookup"><span data-stu-id="03998-111">To Debug a .NET component called by an Orchestration</span></span>  
 <span data-ttu-id="03998-112">オーケストレーションから呼び出される .NET コンポーネントをデバッグするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="03998-112">The following steps demonstrate how to debug a .NET component called by an Orchestration:</span></span>  
  
1.  <span data-ttu-id="03998-113">コンポーネントの [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="03998-113">Open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for your component.</span></span>  
  
2.  <span data-ttu-id="03998-114">コンポーネント内の、オーケストレーションから呼び出されるメソッドにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="03998-114">Set a breakpoint in your component on the method that is called by the orchestration.</span></span>  
  
3.  <span data-ttu-id="03998-115">クリックして、**デバッグ**メニュー**プロセスにアタッチしています.**</span><span class="sxs-lookup"><span data-stu-id="03998-115">Click the **Debug** menu and select **Attach to Process…**</span></span> <span data-ttu-id="03998-116">表示する、**プロセスにアタッチする**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="03998-116">to display the **Attach to Process** dialog.</span></span>  
  
4.  <span data-ttu-id="03998-117">クリックして、**を選択しています.**</span><span class="sxs-lookup"><span data-stu-id="03998-117">Click the **Select…**</span></span> <span data-ttu-id="03998-118">ボタンの横に、**にアタッチ:** を表示するテキスト ボックス、**コードの種類の選択**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="03998-118">button next to the **Attach to:** text box to display the **Select Code Type** dialog.</span></span>  
  
5.  <span data-ttu-id="03998-119">オプションを選択する をクリックします**コードの種類:** を選択し、**マネージ**をクリックし、 **ok**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="03998-119">Click to select the option to **Debug these code types:** and select **Managed** and then click the **OK** button.</span></span>  
  
6.  <span data-ttu-id="03998-120">クリックして選択、 **BTSNTSvc.exe**からプロセス**選択可能なプロセス**をクリックし、**アタッチ**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="03998-120">Click to select the **BTSNTSvc.exe** process from **Available Processes** and then click the **Attach** button.</span></span>  
  
7.  <span data-ttu-id="03998-121">受信ポートを介してオーケストレーションにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="03998-121">Send a message to your orchestration through a receive port.</span></span>  
  
8.  <span data-ttu-id="03998-122">.NET コンポーネント内のブレークポイントで実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="03998-122">The .NET component should be stopped in the breakpoint.</span></span>  
  
9. <span data-ttu-id="03998-123">通常どおり [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でデバッグ作業を行います。</span><span class="sxs-lookup"><span data-stu-id="03998-123">You can perform debugging as usual with [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="03998-124">最良の結果を得るには、.NET コンポーネントをグローバル アセンブリ キャッシュ (GAC) に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03998-124">For best results, the .NET component should be registered in the Global Assembly Cache (GAC).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03998-125">参照</span><span class="sxs-lookup"><span data-stu-id="03998-125">See Also</span></span>  
 <span data-ttu-id="03998-126">[オーケストレーション デバッガーのユーザー インターフェイス](../core/orchestration-debugger-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="03998-126">[Orchestration Debugger User Interface](../core/orchestration-debugger-user-interface.md) </span></span>  
 [<span data-ttu-id="03998-127">オーケストレーションのデバッグ</span><span class="sxs-lookup"><span data-stu-id="03998-127">Debugging Orchestrations</span></span>](../core/debugging-orchestrations.md)