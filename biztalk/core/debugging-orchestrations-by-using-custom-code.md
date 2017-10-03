---
title: "カスタム コードを使用してオーケストレーションのデバッグ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, debugging
- building, debugging
ms.assetid: 94e569fa-8dea-4027-abb5-37b4a8015621
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47f69fa635a90db90c461f75c300334ccc499b94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="debugging-orchestrations-by-using-custom-code"></a>カスタム コードを使用したオーケストレーションのデバッグ
出力を書き込むことができる場合、オーケストレーションは、テスト環境で動作にプロトタイプを作成し、メッセージ フィールドとオーケストレーション変数の値を変更する、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で次のコードを使用して、コンソール**式**図形。  
  
```  
System.Diagnostics.Debug.WriteLine(iResult);  
```  
  
 このセクションを配置する必要があります**式**デバッグ結果を出力できるように、操作を実行する図形のすぐ後の図形です。  
  
 または、単純なを記述する、クラスを含むデバッグ DLL を作成してカスタムのデバッガーには入力形式でメッセージが、オーケストレーションで定義されているし、デバッグ DLL 内で参照として使用するメソッドが含まれています。 詳細については、メッセージをパラメーターとして渡すを参照してください。[オブジェクトを作成するとオブジェクト メソッドの呼び出しに表現を使用する方法](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md)です。  
  
 このメソッドでは、コンボ ボックスまたは他のコントロールを含むデバッグ用のダイアログを表示し、ユーザーに値の変更を許可することができます。その後、編集されたメッセージを取得し、それを戻り値として渡すことができます。  
  
 ブール値変数を設定するかどうか、オーケストレーション デバッグ モードをするには値を変更できるように、オーケストレーションで、ポイントがある任意の場所を示す、ことができますを追加する、**判断**ライブのいずれかの図形分岐を確認する場合に、特定の条件が発生した場合、デバッグ モード変数が True に設定されている場合にのみまたはを実行します。 メソッドの呼び出し、**式**のライブ分岐内の図形、**判断**です。 デバッグ モード変数を False に設定または削除するデバッグが不要になったときに、**判断**図形を完全再コンパイルしてください。  
  
## <a name="to-debug-a-net-component-called-by-an-orchestration"></a>オーケストレーションから呼び出される .NET コンポーネントをデバッグするには  
 オーケストレーションから呼び出される .NET コンポーネントをデバッグするには、次の手順を実行します。  
  
1.  コンポーネントの [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトを開きます。  
  
2.  コンポーネント内の、オーケストレーションから呼び出されるメソッドにブレークポイントを設定します。  
  
3.  クリックして、**デバッグ**メニュー**プロセスにアタッチしています.** 表示する、**プロセスにアタッチする**ダイアログ。  
  
4.  クリックして、**を選択しています.** ボタンの横に、**にアタッチ:**を表示するテキスト ボックス、**コードの種類の選択**ダイアログ。  
  
5.  オプションを選択する をクリックします**コードの種類:**を選択し、**マネージ**をクリックし、 **ok**ボタンをクリックします。  
  
6.  クリックして選択、 **BTSNTSvc.exe**からプロセス**選択可能なプロセス**をクリックし、**アタッチ**ボタンをクリックします。  
  
7.  受信ポートを介してオーケストレーションにメッセージを送信します。  
  
8.  .NET コンポーネント内のブレークポイントで実行が停止します。  
  
9. 通常どおり [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でデバッグ作業を行います。  
  
    > [!NOTE]
    >  最良の結果を得るには、.NET コンポーネントをグローバル アセンブリ キャッシュ (GAC) に登録する必要があります。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション デバッガーのユーザー インターフェイス](../core/orchestration-debugger-user-interface.md)   
 [オーケストレーションのデバッグ](../core/debugging-orchestrations.md)