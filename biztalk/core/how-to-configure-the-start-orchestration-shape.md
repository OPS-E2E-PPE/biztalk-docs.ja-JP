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
ms.openlocfilehash: 6f3e9524198b414fc43e5c4e957ba2f6b6f3f689
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386037"
---
# <a name="how-to-configure-the-start-orchestration-shape"></a>オーケストレーションの開始図形を構成する方法
**オーケストレーションの開始**図形と似ています、**オーケストレーションの呼び出し**図形が非同期的に別のオーケストレーションを呼び出す、**オーケストレーションの開始**図形など、呼び出されたオーケストレーションの処理を完了するを待たず、次に、呼び出し側オーケストレーションの制御フローの開始されます。  
  
 呼び出されたオーケストレーションに渡されるパラメーターを指定することができます。 パラメーターは、メッセージ、変数、ポート参照、ロール リンク、または関連付けセットにすることができます。 **オーケストレーションの開始**図形が受け取ることができる*で*はパラメーターは使用できません*アウト*または*ref*パラメーター。  
  
> [!CAUTION]
>  XmlDocument や XmlNode などの非シリアル化可能なオブジェクトをパラメーターとしてオーケストレーションに渡すことがある場合は失敗します。  
  
 **オーケストレーションの開始**図形をパラメーターとして渡すポートの極性を反転できる唯一の図形では、たとえば、*を使用して*呼び出されたオーケストレーションにポート (送信ポート) に渡すことができます呼び出されたオーケストレーションを使用すると扱うことができますが、*実装*ポート (受信ポート)。 これのみ行う直接バインドを使用するポートとに注意してください。  
  
 **オーケストレーションの開始**図形を使用して別のプロジェクトで参照されているオーケストレーションを呼び出すこともできます。 これにより、一般的なオーケストレーション ワークフロー パターンの再利用するための BizTalk プロジェクト。 参照先のオーケストレーションを呼び出せるようにすることを確認、**型修飾子**呼び出し先オーケストレーションのプロパティに設定されて**パブリック**します。 設定する、**型修飾子**にオーケストレーションのプロパティ**パブリック**、Microsoft では、オーケストレーションを開いて[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、を表示するオーケストレーションの上部にある緑色の開始図形をクリックします。**オーケストレーションのプロパティ**ダイアログとセット、**型修飾子**プロパティを**パブリック**します。 既定値**型修飾子**は**プライベート**します。  
  
 使用する方法の例については**オーケストレーションの開始**図形、SDK サンプル「を実装する Scatter and Gather Pattern」からダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。  
  
### <a name="to-configure-a-start-orchestration-shape"></a>オーケストレーションの開始図形を構成するには  
  
1. 使用して、 **Orchestration Selection**ドロップダウン リスト ボックスで、一覧からオーケストレーションを選択します。  
  
2. 使用して、**オーケストレーション パラメーター**グリッド コントロールをオーケストレーションに渡す引数を指定 — で指定されている、 **Orchestration Selection**ドロップダウン リスト ボックス-開始します。 変数の名前を入力するか、セルのドロップダウン リストから変数をクリックして、各セルの 1 つの変数、変数列のセルでこれらの引数を指定します。  
  
3. 構成する、**オーケストレーションの開始**サービスと、ダイアログ ボックスで指定した引数に従って図形をクリックします**OK**します。 閉じるには、**オーケストレーション構成の開始**] ダイアログ ボックスに変更を加えずに、**オーケストレーションの開始**図形で、[**キャンセル**します。  
  
   > [!CAUTION]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 再帰的なオーケストレーションはサポートされません。 呼び出すかを直接または間接的に呼び出すオーケストレーション A. すべてのオーケストレーションを開始も、オーケストレーション A は、呼び出しや、オーケストレーション B を開始、し、オーケストレーション B を呼び出しまたはを直接、オーケストレーションを開始できません。  
  
## <a name="orchestration-selection-drop-down-list-box"></a>オーケストレーションの選択ドロップダウン リスト ボックス  
 使用可能なオーケストレーションを表示し、1 つを選択するドロップダウン リスト ボックスの下矢印をクリックします。 この一覧には、参照アセンブリも含め、現在のオーケストレーションから開始できるすべてのオーケストレーションが含まれています。  
  
## <a name="orchestration-parameters-grid-control"></a>オーケストレーション パラメーター グリッド コントロール  
 使用して、パラメーターを受け取るオーケストレーションに渡す引数を指定する、**オーケストレーション パラメーター**グリッド コントロール。 グリッドには、4 つの列があります。スコープ、パラメーター名、パラメーターの型、およびパラメーターの方向での変数。 最初の列でのみ変更を行うことができます。その他の列とは、読み取り専用です。  
  
 有効なオーケストレーションを選択すると、そのパラメーターは、パラメーター名、型、およびグリッド コントロールの方向 列を設定します。 各行を引数として渡す変数を選択します。 [スコープ] 列内の変数には、各セルにあるドロップダウン リストから、これらの変数を選択します。 この一覧には、パラメーターの型の隣のセルで指定された型の使用可能なすべての変数が表示されます。 その型の 1 つのオブジェクトにしか使用できない場合はそのオブジェクトはスコープのセル内の変数が自動的に設定されます。 ドロップダウン リストで使用できる変数を選択するには、スコープのセルに変数に入力することもできます。  
  
> [!NOTE]
>  **オーケストレーションの開始**図形をオーケストレーションを開始する、このダイアログ ボックスで選択する「オーケストレーション パラメーター」は実際にはオーケストレーション変数を参照してください。  
  
 実行しているオーケストレーションが定義されているパラメーターを持たない場合はこのダイアログ ボックスでグリッド コントロールは使用できません。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [作成する方法について呼び出されたオーケストレーションに受信サブスクリプション](../core/how-to-create-receive-subscriptions-at-invoked-orchestrations.md) 
  
## <a name="see-also"></a>参照  
 [オーケストレーションの呼び出し図形を構成する方法](../core/how-to-configure-the-call-orchestration-shape.md)