---
title: オーケストレーションの呼び出し図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Orchestration shape [Orchestration Designer], parameters
- Call Orchestration shape [Orchestration Designer], configuring
- Call Orchestration shape [Orchestration Designer], about Call Orchestration shapes
- configuring [Orchestration Designer], Call Orchestration shapes
- Call Orchestration shape [Orchestration Designer]
- nonserializable objects
- orchestrations, nonserializable objects
- Call Orchestration shape [Orchestration Designer], referencing orchestrations
- orchestrations, parameters
ms.assetid: 718ce2a0-ac08-4662-8b4e-1be279dbc749
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aab9f1ab84836d436ea1570b7d63f8a3cc0c0064
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981035"
---
# <a name="how-to-configure-the-call-orchestration-shape"></a>オーケストレーションの呼び出し図形を構成する方法
**オーケストレーションの呼び出し**を別のプロジェクトで参照されているオーケストレーションを同期的に呼び出す図形を使用することができます。 これにより、一般的なオーケストレーション ワークフロー パターンを BizTalk プロジェクト間で再利用できるようになります。 同期的に入れ子になった別のオーケストレーションを呼び出すと、**オーケストレーションの呼び出し**図形の外側のオーケストレーションが、入れ子になったオーケストレーションを続行する前に完了を待ちます。  
  
 ネストされているオーケストレーションに渡すパラメーターを指定することもできます。 パラメーターとして指定できるのは、メッセージ、変数、ポート参照、ロール リンク、または関連付けセットです。 渡されたポート参照、ロール リンク、および関連付けセットのすべてを封筒のように実行します。 外側のオーケストレーションに情報が送信に使用できる、入れ子になったオーケストレーション情報を指定します。  
  
> [!CAUTION]
>  XmlDocument や XmlNode などのシリアル化できないオブジェクトをパラメーターとしてオーケストレーションに渡すと失敗します。  
  
 使用する方法の例については**オーケストレーションの呼び出し**図形は、「 [CallOrchestration (BizTalk Server サンプル)](../core/callorchestration-biztalk-server-sample.md)します。  
  
### <a name="to-configure-a-call-orchestration-shape"></a>オーケストレーションの呼び出し図形を構成するには  
  
1. 使用して、 **Orchestration Selection**ドロップダウン リスト ボックスで、一覧からオーケストレーションを選択します。  
  
2. 使用して、**オーケストレーション パラメーター**グリッド コントロールをオーケストレーションに渡す引数を指定 — で指定されている、 **Orchestration Selection**ドロップダウン リスト ボックス-呼び出されます。 これらの引数は、[変数] 列の各セルに 1 つずつ変数の名前を入力するか、各セルのドロップダウン リストでいずれかの変数をクリックすることによって指定します。  
  
3. 構成する、**オーケストレーションの呼び出し**サービスと、ダイアログ ボックスで指定した引数に従って図形をクリックします**OK**します。 閉じるには、**オーケストレーション構成の呼び出し**] ダイアログ ボックスに変更を加えずに、**オーケストレーションの呼び出し**図形で、[**キャンセル**します。  
  
   > [!CAUTION]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、再帰的なオーケストレーションはサポートされていません。 オーケストレーション A でオーケストレーション B を呼び出すか開始すると、オーケストレーション B でオーケストレーション A を直接呼び出したり開始したりすることはできなくなり、直接または間接的にオーケストレーション A を呼び出すオーケストレーションの呼び出しや開始もできなくなります。  
  
## <a name="referenced-orchestrations"></a>参照されているオーケストレーション  
 参照されているオーケストレーションを呼び出せるようにするには、呼び出し先オーケストレーションに対して次のプロパティが構成されていることを確認します。  
  
- 設定、**型修飾子**プロパティを**パブリック**呼び出し先オーケストレーションします。 設定する、**型修飾子**にオーケストレーションのプロパティ**パブリック**、Microsoft では、オーケストレーションを開いて[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、を表示するオーケストレーションの上部にある緑色の開始図形をクリックします。**オーケストレーションのプロパティ**ダイアログとセット、**型修飾子**プロパティを**パブリック**します。  
  
- 設定、 **Activate**プロパティをオーケストレーションの当初の受信図形の**False**します。  
  
## <a name="orchestration-selection-drop-down-list-box"></a>[Orchestration Selection] ボックス  
 ドロップダウン リスト ボックスの下矢印をクリックして使用可能なサービスを参照し、いずれか 1 つを選択します。 この一覧には、参照アセンブリも含め、現在のオーケストレーションから呼び出せるすべてのサービスが表示されます。  
  
## <a name="orchestration-parameters-grid-control"></a>[オーケストレーション パラメーター] グリッド コントロール  
 使用して、パラメーターを受け取るオーケストレーションに渡す引数を指定する、**オーケストレーション パラメーター**グリッド コントロール。 グリッドが 4 つの列: 変数のスコープ、パラメーター名、パラメーターの型、およびパラメーターの方向。 変更を加えられるのは 1 列目のみで、その他の列は読み取り専用になっています。  
  
 有効なオーケストレーションを選択すると、そのパラメーターは、グリッド コントロールのパラメーターの名前、型および方向の列を設定します。 次に、引数として渡す変数を各行で選択します。 これらの変数は、[スコープ内の変数] 列の各セルにあるドロップダウン リストから選択します。 このドロップダウン リストには、隣の [パラメーターの種類] セルで指定された種類の使用可能な変数がすべて表示されます。 その種類の使用可能なオブジェクトが 1 つしかない場合、[スコープ内の変数] セルにはそのオブジェクトが自動的に設定されます。 [スコープ内の変数] セルのドロップダウン リストにある変数を直接入力して選択することもできます。  
  
> [!NOTE]
>  **オーケストレーションの呼び出し**図形がオーケストレーションを呼び出し、このダイアログ ボックスで選択する「オーケストレーション パラメーター」は実際にはオーケストレーション変数を参照してください。  
  
 呼び出し先オーケストレーションでパラメーターが定義されていない場合、このダイアログ ボックスのグリッド コントロールは使用できません。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの開始図形を構成する方法](../core/how-to-configure-the-start-orchestration-shape.md)