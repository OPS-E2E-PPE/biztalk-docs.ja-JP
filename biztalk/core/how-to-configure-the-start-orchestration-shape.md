---
title: オーケストレーションの開始図形を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Start Orchestration shapes
- Start Orchestration shape [Orchestration Designer], parameters
- Start Orchestration shape [Orchestration Designer], configuring
- orchestrations, starting
- Start Orchestration shape [Orchestration Designer]
- Start Orchestration shape [Orchestration Designer], starting orchestrations
- Start Orchestration shape [Orchestration Designer], about Star Orchestration shape
ms.assetid: 9d01c41e-9bc5-4c1c-a869-b2f0df13036a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f8181849b700939ba86f55cd372b80ed2ebf70e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249666"
---
# <a name="how-to-configure-the-start-orchestration-shape"></a>オーケストレーションの開始図形を構成する方法
**オーケストレーションの開始**図形がに似ていますが、**オーケストレーションの呼び出し**図形が使用した非同期の別のオーケストレーションを呼び出す、**オーケストレーションの開始**図形: 呼び出されたオーケストレーションがその作業を終了するを待たず、呼び出しを超える、呼び出し側オーケストレーションの制御フローの開始されます。  
  
 呼び出されたオーケストレーションに渡すパラメーターを指定することができます。 パラメーターとして指定できるのは、メッセージ、変数、ポート参照、ロール リンク、または関連付けセットです。 **オーケストレーションの開始**図形が受け取ることができる*で*パラメーター; ことはできません*アウト*または*ref*パラメーター。  
  
> [!CAUTION]
>  XmlDocument や XmlNode などのシリアル化できないオブジェクトをパラメーターとしてオーケストレーションに渡すことは失敗します。  
  
 **オーケストレーションの開始**図形をパラメーターとして渡すポートの極性を反転できる唯一の図形では、たとえば、*を使用して*呼び出されたオーケストレーションのポート (送信ポート) に渡すことができます呼び出されたオーケストレーションを使用すると扱うことができますが、*実装*ポート (受信ポート)。 ただし、これを実行できるのは直接バインドを使用するポートだけです。  
  
 **オーケストレーションの開始**図形は、別のプロジェクトで参照されているオーケストレーションの呼び出しにも使用できます。 これにより、一般的なオーケストレーション ワークフロー パターンを BizTalk プロジェクト間で再利用できるようになります。 呼び出し可能である参照先のオーケストレーションでは、いることを確認、**型修飾子**呼び出されたオーケストレーションのプロパティに設定されて**パブリック**です。 設定する、**型修飾子**にオーケストレーションのプロパティを**パブリック**、Microsoft では、オーケストレーションを開いて[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、を表示するオーケストレーションの上部にある緑のスタート図形をクリックして**オーケストレーションのプロパティ**ダイアログとセット、**型修飾子**プロパティを**パブリック**です。 既定値**型修飾子**は**プライベート**です。  
  
 使用する方法の例については**オーケストレーションの開始**図形、SDK サンプルの「実装 Scatter and Gather Pattern」からダウンロード[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。  
  
### <a name="to-configure-a-start-orchestration-shape"></a>オーケストレーションの開始図形を構成するには  
  
1.  使用して、 **Orchestration Selection**ドロップダウン リスト ボックス、一覧から、オーケストレーションを選択します。  
  
2.  使用して、**オーケストレーション パラメーター**グリッド コントロールをオーケストレーションに渡す引数を指定: で指定した、 **Orchestration Selection**ドロップダウン リスト ボックス-に開始されます。 これらの引数は、[変数] 列の各セルに 1 つずつ変数の名前を入力するか、各セルのドロップダウン リストでいずれかの変数をクリックすることによって指定します。  
  
3.  構成する、**オーケストレーションの開始**サービスと、ダイアログ ボックスで指定した引数に応じて図形をクリックして**OK**です。 閉じるには、**オーケストレーション構成の開始**に変更を加えずに ダイアログ ボックス、**オーケストレーションの開始**図形をクリックして**キャンセル**です。  
  
    > [!CAUTION]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、再帰的なオーケストレーションはサポートされていません。 オーケストレーション A でオーケストレーション B を呼び出すか開始すると、オーケストレーション B でオーケストレーション A を直接呼び出したり開始したりすることはできなくなり、直接または間接的にオーケストレーション A を呼び出すオーケストレーションの呼び出しや開始もできなくなります。  
  
## <a name="orchestration-selection-drop-down-list-box"></a>[Orchestration Selection] ボックス  
 ドロップダウン リスト ボックスの下矢印をクリックして使用可能なオーケストレーションを参照し、いずれか 1 つを選択します。 この一覧には、参照アセンブリも含め、現在のオーケストレーションから開始できるすべてのオーケストレーションが表示されます。  
  
## <a name="orchestration-parameters-grid-control"></a>[オーケストレーション パラメーター] グリッド コントロール  
 使用してパラメーター化されたオーケストレーションに渡す引数を指定する、**オーケストレーション パラメーター**グリッド コントロール。 グリッドには、4 つの列:、変数のスコープ パラメーターの名前、パラメーターの型、パラメーターの方向。 変更を加えられるのは 1 列目のみで、その他の列は読み取り専用になっています。  
  
 有効なオーケストレーションを選択すると、そのパラメーターの値がグリッド コントロールの [パラメーター名]、[パラメーターの種類]、および [パラメーターの方向] 列に設定されます。 次に、引数として渡す変数を各行で選択します。 これらの変数は、[スコープ内の変数] 列の各セルにあるドロップダウン リストから選択します。 このドロップダウン リストには、隣の [パラメーターの種類] セルで指定された種類の使用可能な変数がすべて表示されます。 その種類の使用可能なオブジェクトが 1 つしかない場合、[スコープ内の変数] セルにはそのオブジェクトが自動的に設定されます。 [スコープ内の変数] セルのドロップダウン リストにある変数を直接入力して選択することもできます。  
  
> [!NOTE]
>  **オーケストレーションの開始**図形がオーケストレーションを開始、このダイアログ ボックスで選択する「オーケストレーション パラメーター」は実際にはオーケストレーション変数を参照してください。  
  
 実行するオーケストレーションでパラメーターが定義されていない場合、このダイアログ ボックスのグリッド コントロールは使用できません。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [作成する方法で呼び出されたオーケストレーションのサブスクリプションが表示されます。](../core/how-to-create-receive-subscriptions-at-invoked-orchestrations.md) 
  
## <a name="see-also"></a>参照  
 [オーケストレーションの呼び出し図形を構成する方法](../core/how-to-configure-the-call-orchestration-shape.md)