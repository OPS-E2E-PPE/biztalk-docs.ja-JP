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
# <a name="debugging-orchestrations-by-using-custom-code"></a>カスタム コードを使用したオーケストレーションのデバッグ
オーケストレーションがテスト環境で使用するか、またはプロトタイプを作成し、メッセージ フィールドとオーケストレーション変数の値を変更するは、出力を書き込むことができます、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で次のコードを使用して、コンソール**式**図形。  
  
```  
System.Diagnostics.Debug.WriteLine(iResult);  
```  
  
 これを配置する必要がある**式**デバッグの結果を出力できるように、操作を実行する図形の直後後の図形。  
  
 または、単純なを記述することができます、クラスを使用してデバッグ DLL を作成してカスタムのデバッガーには形式のメッセージがオーケストレーションで定義されているし、デバッグ DLL で参照されている入力として受け取るメソッドが含まれています。 メッセージをパラメーターとして渡すことの詳細については、[オブジェクトを作成してオブジェクトのメソッドを呼び出す式を使用する方法](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md)を参照してください。  
  
 このメソッドでは、コンボ ボックスまたは他のコントロールを含むデバッグ用のダイアログを表示し、ユーザーに値の変更を許可することができます。その後、編集されたメッセージを取得し、それを戻り値として渡すことができます。  
  
 追加できるかどうか、オーケストレーションがデバッグ モードでは、その値を変更できるように、オーケストレーションで、ポイントがある任意の場所を示すブール値変数を設定、**判断**ライブのいずれかの図形実行、デバッグ モード変数が True に設定されている場合にのみ、または特定の条件を確認することが発生したときに分岐します。 メソッドを呼び出す、**式**のライブ分岐内の図形、**判断**します。 False に、デバッグ モード変数を設定または削除するデバッグが不要になったときに、**判断**なくなった完全再コンパイルしてください。  
  
## <a name="to-debug-a-net-component-called-by-an-orchestration"></a>オーケストレーションから呼び出される .NET コンポーネントをデバッグするには  
 オーケストレーションから呼び出される .NET コンポーネントをデバッグするには、次の手順を実行します。  
  
1. コンポーネントの [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトを開きます。  
  
2. コンポーネント内の、オーケストレーションから呼び出されるメソッドにブレークポイントを設定します。  
  
3. をクリックして、**デバッグ**メニュー選択し、**プロセスにアタッチしています.** 表示する、**プロセスにアタッチ**ダイアログ。  
  
4. をクリックして、**を選択しています.** ボタンの横に、**にアタッチ:** を表示するテキスト ボックス、**コードの種類の選択**ダイアログ。  
  
5. オプションを選択する をクリックします**コードの種類:** 選択と**マネージ**順にクリックします、 **ok**ボタン。  
  
6. クリックして選択し、 **BTSNTSvc.exe**からプロセス**選択可能なプロセス**順にクリックします、**アタッチ**ボタン。  
  
7. 受信ポートを介してオーケストレーションにメッセージを送信します。  
  
8. .NET コンポーネント内のブレークポイントで実行が停止します。  
  
9. 通常どおり [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でデバッグ作業を行います。  
  
    > [!NOTE]
    >  最良の結果を得るには、.NET コンポーネントをグローバル アセンブリ キャッシュ (GAC) に登録する必要があります。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション デバッガーのユーザー インターフェイス](../core/orchestration-debugger-user-interface.md)   
 [オーケストレーションのデバッグ](../core/debugging-orchestrations.md)