---
title: オーケストレーションの開始図形を構成する方法 |Microsoft Docs
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
ms.openlocfilehash: 4877d775b30f7ab407f57ebf2679f8cb65a0ef08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974915"
---
# <a name="how-to-configure-the-start-orchestration-shape"></a>オーケストレーションの開始図形を構成する方法
**オーケストレーションの開始**図形と似ています、**オーケストレーションの呼び出し**図形が非同期的に別のオーケストレーションを呼び出す、**オーケストレーションの開始**図形など、呼び出されたオーケストレーションの処理を完了するを待たず、次に、呼び出し側オーケストレーションの制御フローの開始されます。  
  
 呼び出されたオーケストレーションに渡すパラメーターを指定することができます。 パラメーターとして指定できるのは、メッセージ、変数、ポート参照、ロール リンク、または関連付けセットです。 **オーケストレーションの開始**図形が受け取ることができる*で*はパラメーターは使用できません*アウト*または*ref*パラメーター。  
  
> [!CAUTION]
>  XmlDocument や XmlNode などの非シリアル化可能なオブジェクトをパラメーターとしてオーケストレーションに渡すことがある場合は失敗します。  
  
 **オーケストレーションの開始**図形をパラメーターとして渡すポートの極性を反転できる唯一の図形では、たとえば、*を使用して*呼び出されたオーケストレーションにポート (送信ポート) に渡すことができます呼び出されたオーケストレーションを使用すると扱うことができますが、*実装*ポート (受信ポート)。 ただし、これを実行できるのは直接バインドを使用するポートだけです。  
  
 **オーケストレーションの開始**図形を使用して別のプロジェクトで参照されているオーケストレーションを呼び出すこともできます。 これにより、一般的なオーケストレーション ワークフロー パターンを BizTalk プロジェクト間で再利用できるようになります。 参照先のオーケストレーションを呼び出せるようにすることを確認、**型修飾子**呼び出し先オーケストレーションのプロパティに設定されて**パブリック**します。 設定する、**型修飾子**にオーケストレーションのプロパティ**パブリック**、Microsoft では、オーケストレーションを開いて[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、を表示するオーケストレーションの上部にある緑色の開始図形をクリックします。**オーケストレーションのプロパティ**ダイアログとセット、**型修飾子**プロパティを**パブリック**します。 既定値**型修飾子**は**プライベート**します。  
  
 使用する方法の例については**オーケストレーションの開始**図形、SDK サンプル「を実装する Scatter and Gather Pattern」からダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。  
  
### <a name="to-configure-a-start-orchestration-shape"></a>オーケストレーションの開始図形を構成するには  
  
1. 使用して、 **Orchestration Selection**ドロップダウン リスト ボックスで、一覧からオーケストレーションを選択します。  
  
2. 使用して、**オーケストレーション パラメーター**グリッド コントロールをオーケストレーションに渡す引数を指定 — で指定されている、 **Orchestration Selection**ドロップダウン リスト ボックス-開始します。 これらの引数は、[変数] 列の各セルに 1 つずつ変数の名前を入力するか、各セルのドロップダウン リストでいずれかの変数をクリックすることによって指定します。  
  
3. 構成する、**オーケストレーションの開始**サービスと、ダイアログ ボックスで指定した引数に従って図形をクリックします**OK**します。 閉じるには、**オーケストレーション構成の開始**] ダイアログ ボックスに変更を加えずに、**オーケストレーションの開始**図形で、[**キャンセル**します。  
  
   > [!CAUTION]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、再帰的なオーケストレーションはサポートされていません。 オーケストレーション A でオーケストレーション B を呼び出すか開始すると、オーケストレーション B でオーケストレーション A を直接呼び出したり開始したりすることはできなくなり、直接または間接的にオーケストレーション A を呼び出すオーケストレーションの呼び出しや開始もできなくなります。  
  
## <a name="orchestration-selection-drop-down-list-box"></a>[Orchestration Selection] ボックス  
 ドロップダウン リスト ボックスの下矢印をクリックして使用可能なオーケストレーションを参照し、いずれか 1 つを選択します。 この一覧には、参照アセンブリも含め、現在のオーケストレーションから開始できるすべてのオーケストレーションが表示されます。  
  
## <a name="orchestration-parameters-grid-control"></a>[オーケストレーション パラメーター] グリッド コントロール  
 使用して、パラメーターを受け取るオーケストレーションに渡す引数を指定する、**オーケストレーション パラメーター**グリッド コントロール。 グリッドが 4 つの列: 変数のスコープ、パラメーター名、パラメーターの型、およびパラメーターの方向。 変更を加えられるのは 1 列目のみで、その他の列は読み取り専用になっています。  
  
 有効なオーケストレーションを選択すると、そのパラメーターの値がグリッド コントロールの [パラメーター名]、[パラメーターの種類]、および [パラメーターの方向] 列に設定されます。 次に、引数として渡す変数を各行で選択します。 これらの変数は、[スコープ内の変数] 列の各セルにあるドロップダウン リストから選択します。 このドロップダウン リストには、隣の [パラメーターの種類] セルで指定された種類の使用可能な変数がすべて表示されます。 その種類の使用可能なオブジェクトが 1 つしかない場合、[スコープ内の変数] セルにはそのオブジェクトが自動的に設定されます。 [スコープ内の変数] セルのドロップダウン リストにある変数を直接入力して選択することもできます。  
  
> [!NOTE]
>  **オーケストレーションの開始**図形をオーケストレーションを開始する、このダイアログ ボックスで選択する「オーケストレーション パラメーター」は実際にはオーケストレーション変数を参照してください。  
  
 実行するオーケストレーションでパラメーターが定義されていない場合、このダイアログ ボックスのグリッド コントロールは使用できません。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [作成する方法について呼び出されたオーケストレーションに受信サブスクリプション](../core/how-to-create-receive-subscriptions-at-invoked-orchestrations.md) 
  
## <a name="see-also"></a>参照  
 [オーケストレーションの呼び出し図形を構成する方法](../core/how-to-configure-the-call-orchestration-shape.md)