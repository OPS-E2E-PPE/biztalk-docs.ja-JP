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
ms.openlocfilehash: f20025f771f28f91e1fe40b10bfc0e999685eb68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386117"
---
# <a name="how-to-configure-the-call-orchestration-shape"></a>オーケストレーションの呼び出し図形を構成する方法
**オーケストレーションの呼び出し**を別のプロジェクトで参照されているオーケストレーションを同期的に呼び出す図形を使用することができます。 これにより、一般的なオーケストレーション ワークフロー パターンの再利用するための BizTalk プロジェクト。 同期的に入れ子になった別のオーケストレーションを呼び出すと、**オーケストレーションの呼び出し**図形の外側のオーケストレーションが、入れ子になったオーケストレーションを続行する前に完了を待ちます。  
  
 入れ子になったオーケストレーションに渡されるパラメーターを指定することができます。 パラメーターは、メッセージ、変数、ポート参照、ロール リンク、または関連付けセットにすることができます。 渡されたポート参照、ロール リンク、および関連付けセットのすべてを封筒のように実行します。 外側のオーケストレーションに情報が送信に使用できる、入れ子になったオーケストレーション情報を指定します。  
  
> [!CAUTION]
>  XmlDocument や XmlNode などのシリアル化できないオブジェクトをパラメーターとしてオーケストレーションに渡すことがある場合は失敗します。  
  
 使用する方法の例については**オーケストレーションの呼び出し**図形は、「 [CallOrchestration (BizTalk Server サンプル)](../core/callorchestration-biztalk-server-sample.md)します。  
  
### <a name="to-configure-a-call-orchestration-shape"></a>オーケストレーションの呼び出し図形を構成するには  
  
1. 使用して、 **Orchestration Selection**ドロップダウン リスト ボックスで、一覧からオーケストレーションを選択します。  
  
2. 使用して、**オーケストレーション パラメーター**グリッド コントロールをオーケストレーションに渡す引数を指定 — で指定されている、 **Orchestration Selection**ドロップダウン リスト ボックス-呼び出されます。 変数の名前を入力するか、セルのドロップダウン リストから変数をクリックして、各セルの 1 つの変数、変数列のセルでこれらの引数を指定します。  
  
3. 構成する、**オーケストレーションの呼び出し**サービスと、ダイアログ ボックスで指定した引数に従って図形をクリックします**OK**します。 閉じるには、**オーケストレーション構成の呼び出し**] ダイアログ ボックスに変更を加えずに、**オーケストレーションの呼び出し**図形で、[**キャンセル**します。  
  
   > [!CAUTION]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 再帰的なオーケストレーションはサポートされません。 呼び出すかを直接または間接的に呼び出すオーケストレーション A. すべてのオーケストレーションを開始も、オーケストレーション A は、呼び出しや、オーケストレーション B を開始、し、オーケストレーション B を呼び出しまたはを直接、オーケストレーションを開始できません。  
  
## <a name="referenced-orchestrations"></a>参照されているオーケストレーション  
 呼び出せるようにする参照先のオーケストレーションでは、呼び出し先オーケストレーションの次のプロパティが構成されていることを確認します。  
  
- 設定、**型修飾子**プロパティを**パブリック**呼び出し先オーケストレーションします。 設定する、**型修飾子**にオーケストレーションのプロパティ**パブリック**、Microsoft では、オーケストレーションを開いて[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、を表示するオーケストレーションの上部にある緑色の開始図形をクリックします。**オーケストレーションのプロパティ**ダイアログとセット、**型修飾子**プロパティを**パブリック**します。  
  
- 設定、 **Activate**プロパティをオーケストレーションの当初の受信図形の**False**します。  
  
## <a name="orchestration-selection-drop-down-list-box"></a>オーケストレーションの選択ドロップダウン リスト ボックス  
 利用可能なサービスを表示し、1 つを選択するドロップダウン リスト ボックスの下矢印をクリックします。 この一覧には、参照アセンブリも含め、現在のオーケストレーションから呼び出すことができるすべてのサービスが含まれています。  
  
## <a name="orchestration-parameters-grid-control"></a>オーケストレーション パラメーター グリッド コントロール  
 使用して、パラメーターを受け取るオーケストレーションに渡す引数を指定する、**オーケストレーション パラメーター**グリッド コントロール。 グリッドには、4 つの列があります。スコープ、パラメーター名、パラメーターの型、およびパラメーターの方向での変数。 最初の列でのみ変更を行うことができます。その他の列とは、読み取り専用です。  
  
 有効なオーケストレーションを選択すると、そのパラメーターは、グリッド コントロールのパラメーターの名前、型および方向の列を設定します。 各行を引数として渡す変数を選択します。 [スコープ] 列内の変数には、各セルにあるドロップダウン リストから、これらの変数を選択します。 この一覧には、パラメーターの型の隣のセルで指定された型の使用可能なすべての変数が表示されます。 その型の 1 つのオブジェクトにしか使用できない場合はそのオブジェクトはスコープのセル内の変数が自動的に設定されます。 ドロップダウン リストで使用できる変数を選択するには、スコープのセルに変数に入力することもできます。  
  
> [!NOTE]
>  **オーケストレーションの呼び出し**図形がオーケストレーションを呼び出し、このダイアログ ボックスで選択する「オーケストレーション パラメーター」は実際にはオーケストレーション変数を参照してください。  
  
 呼び出しているオーケストレーションが定義されているパラメーターを持たない場合はこのダイアログ ボックスでグリッド コントロールは使用できません。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの開始図形を構成する方法](../core/how-to-configure-the-start-orchestration-shape.md)