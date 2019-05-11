---
title: Functoid 入力パラメーターを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bts10.mapper.functoid.inputs
ms.assetid: 2c8f773a-932c-423d-b3fe-724265304b0a
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75c2d7997f76df6e1b4983a896d409a93c628872
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341516"
---
# <a name="how-to-configure-functoid-input-parameters"></a>Functoid 入力パラメーターを構成する方法
マップ内の Functoid に対する入力パラメーターを適切に構成する操作は、最も重要な操作の 1 つです。ただし、Functoid を使用する際にエラーが発生する可能性があるので注意して行う必要があります。 Functoid の入力パラメーターは次のように構成できます。  
  
- 接続のスキーマ ノードと個々 の functoid (ドラッグ アンド ドロップを functoid にスキーマ ノードからマウス) で表示可能な入力リンクを作成します。  
  
- 使用して入力パラメーターの一覧を直接編集、**構成\<Functoid\> Functoid**  ダイアログ ボックス。  
  
  これらのメソッドを使用して、functoid の入力パラメーターを構成する手順について説明します。  
  
  ドラッグして Functoid の入力パラメーターを設定する方法は、XPath 仕様を含む入力パラメーターを送信元スキーマに指定する場合に便利です。 スキーマ ノードおよび functoid の入力パラメーターを作成する方法の詳細については、次を参照してください。[マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)します。 ただし、**構成\<Functoid\> Functoid**  ダイアログ ボックスは、明確なメカニズムの functoid へのすべての入力パラメーターを表示、作成と、定数のパラメーターを変更、およびの必要に応じて入力パラメーターの順序の再配置します。  
  
  グリッド ページで Functoid の入力パラメーターを直接構成する (マウスのドラッグ アンド ドロップによって送信元スキーマ ノードから線を描画して Functoid にリンクする) 場合、入力数が最大値に達すると、カーソルが禁止の状態に変わります。 また、ステータス バーに理由が表示されます。 次の図は、入力リンクを 1 つだけ受け付ける Functoid を示しています。  
  
  ![Functoid 入力パラメーターを構成するための NO 状態](../core/media/configure-input-parameters-no-state.gif "Configure_input_parameters_NO_state")  
  
  使用してスクリプトの作成とテーブル ループ functoid を構成することができます、**構成\<Functoid\> Functoid**  ダイアログ ボックス。 Functoid を構成する方法については、次を参照してください。[スクリプト Functoid を構成する方法](../core/how-to-configure-the-scripting-functoid.md)と[テーブル ループとテーブル抽出 Functoid を構成する方法](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
## <a name="what-is-an-input-parameter"></a>入力パラメーターとは  
 入力パラメーターには、次のいずれかを指定できます。  
  
-   送信元スキーマ ノードから Functoid へのリンク  
  
-   Functoid から別の有効な Functoid へのリンク  
  
-   定数値  
  
> [!NOTE]
>  など一部の functoid がある**日付**、**時間**、**日付と時刻**、および**Nil**、すべての入力パラメーターを必要としません。  
  
 次の図に、2 つの入力パラメーター (Input[0] および Input[1]) と定数パラメーター (Input[2]) を持つ Functoid (赤で強調表示) を示します。  
  
 ![Functoid に入力パラメーターの表示](../core/media/identifying-input-parameters.gif "Identifying_input_parameters")  
  
## <a name="to-open-the-configure-functoid-functoid-dialog-box"></a>構成を開く\<Functoid\> Functoid のダイアログ ボックス  
 開くことができます、**構成\<Functoid\> Functoid**  ダイアログ ボックスで、次の方法のいずれか。  
  
-   関連するグリッド ページで、functoid を右クリックし、順にクリックします**Functoid 入力の構成**します。  
  
-   入力パラメーターを構成する Functoid をダブルクリックします。  
  
-   Functoid を選択し、省略記号ボタンをクリックし (**.**) Visual studio の**プロパティ**ウィンドウ。  
  
-   Functoid を選択し、Enter キーを押します。  
  
-   Functoid を選択し、Ctrl キーを押しながら M キーを押し、Ctrl キーを押しながら I キーを押します。 マッパーのショートカット キーの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)します。  
  
### <a name="to-insert-constant-input-parameters"></a>定数の入力パラメーターを挿入するには  
  
1.  **構成\<Functoid\> Functoid**ダイアログ ボックスで、 **Functoid 入力の**タブ。  
  
    > [!NOTE]
    >  **Functoid 入力の**タブは既定で選択します。  
  
2.  をクリックして、 ![functoid への定数入力パラメーターの追加](../core/media/add-input-parameters.gif "Add_input_parameters")ボタンをクリックします。 新しい行が追加されます。  
  
3.  新しい入力パラメーターの値を入力し、クリックして**OK**します。  
  
    > [!NOTE]
    >  追加ボタンが使用できない場合は、Functoid が入力パラメーターを受け入れないか、入力パラメーターを必要としていません。または、許可される入力パラメーターの最大数に達しています。  
  
### <a name="to-edit-existing-constant-input-parameters"></a>既存の定数入力パラメーターを編集するには  
  
1.  **構成\<Functoid\> Functoid**ダイアログ ボックスで、既存の定数入力パラメーターを編集する をクリックします。 現在の値が選択されています。  
  
    > [!IMPORTANT]
    >  編集できるのは定数入力のパラメーターだけです。 その他の種類の入力パラメーターは編集できません。 順序の並べ替えまたは削除のみ行うことができます。  
  
2.  をクリックして、![定数入力パラメーターの編集](../core/media/edit-input-parameters.gif "Edit_input_parameters")ボタンをクリックします。 定数の値に必要な変更を行い、をクリックし、 **OK**します。  
  
     この代わりに、定数入力パラメーターをダブルクリックして編集するか、または F2 キーを押すこともできます。  
  
## <a name="to-select-multiple-input-parameters"></a>複数の入力パラメーターを選択するには  
 Ctrl キーを押しながら目的の行をクリックして複数の入力パラメーターを選択した後、次のいずれかの操作を実行できます。 Ctrl キーを押しながら A キーを押すと、すべての行を選択できます。  
  
-   選択項目を上下に移動します。  
  
    > [!NOTE]
    >  一括選択に一番上の行または一番下の行が含まれる場合は、選択項目を上下に移動することはできません。  
  
-   選択項目を並べ替えます。  
  
-   選択項目を削除します。  
  
### <a name="to-change-the-order-of-existing-input-parameters"></a>既存の入力パラメーターの順序を変更するには  
  
1.  **構成\<Functoid\> Functoid**ダイアログ ボックスで、既存の入力パラメーターの入力パラメーターの順序付きリストで別の位置に移動する をクリックします。  
  
2.  をクリックして、![の一覧で上へ移動](../core/media/move-up-button.gif "Move_up_button")パラメーター リストで、パラメーターを上に移動するボタンをクリックします。 選択した入力パラメーターが目的の位置になるまで必要なだけ繰り返します。 または、上方向キーを押してもかまいません。 マッパーのショートカット キーの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)します。  
  
     -または-  
  
     をクリックして、![一覧で下へ移動](../core/media/move-down-button.gif "Move_down_button")パラメーター リストで、パラメーターを下に移動するボタンをクリックします。 選択した入力パラメーターが目的の位置になるまで必要なだけ繰り返します。 または、下方向キーを押してもかまいません。 マッパーのショートカット キーの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)します。  
  
    > [!IMPORTANT]
    >  のみからの入力のシーケンスを並べ替えることができます、**構成\<Functoid\> Functoid**  ダイアログ ボックス。 最上位または最下位の行を選択した場合、![の一覧で上へ移動](../core/media/move-up-button.gif "Move_up_button")または![一覧で下へ移動](../core/media/move-down-button.gif "Move_down_button")ボタンが無効になります、それぞれします。  
  
### <a name="to-delete-an-input-parameter-by-deleting-the-input-link"></a>入力リンクを削除して入力パラメーターを削除するには  
  
1.  関連するグリッド ページで、削除する入力パラメーターに対応する入力リンクをクリックします。  
  
2.  **編集** メニューのをクリックして**削除**します。  
  
    > [!NOTE]
    >  またはを DEL キーを押してまたは関連するグリッド ページで、リンクを右クリックし、をクリックして**削除**ショートカット メニューから。  
  
    > [!IMPORTANT]
    >  入力リンクは、確認メッセージが表示されずに削除されます。 よくわからない場合は削除をいつでも元に戻すことができます。 元に戻す/やり直し操作の詳細については、次を参照してください。[を元に戻すまたはユーザーの操作をやり直す方法](../core/how-to-undo-or-redo-user-operations.md)します。  
  
### <a name="to-delete-existing-input-parameters-within-the-configure-functoid-functoid-dialog-box"></a>既存の入力パラメーターの構成を削除する\<Functoid\> Functoid のダイアログ ボックス  
  
1.  **構成\<Functoid\> Functoid**ダイアログ ボックスで、既存の入力パラメーターを削除する をクリックします。  
  
    > [!NOTE]
    >  この方法を使用して、入力パラメーター (入力リンクに対応するパラメーターを含む) を削除できます。  
  
2.  をクリックして、![選択項目の削除](../core/media/delete-button.gif "Delete_button")ボタンをクリックします。 選択した既存の入力パラメーターが、パラメーター一覧から削除されます。 **[OK]** をクリックします。  
  
     または、削除する行を選択して、キーボードの Del キーを押します。  
  
    > [!IMPORTANT]
    >  入力パラメーターは、確認メッセージが表示されずに削除されます。 よくわからない場合は削除をいつでも元に戻すことができます。 元に戻す/やり直し操作の詳細については、次を参照してください。[を元に戻すまたはユーザーの操作をやり直す方法](../core/how-to-undo-or-redo-user-operations.md)します。  
  
    > [!NOTE]
    >  削除ボタンは、パラメーターの一覧に入力パラメーターがないと使用できません。  
  
## <a name="to-set-labels-and-comments-for-functoids"></a>Functoid のラベルおよびコメントを設定するには  
 Functoid を使用してのラベルおよびコメントを設定することができます、**構成\<Functoid\> Functoid**  ダイアログ ボックス。  
  
1.  **構成\<Functoid\> Functoid**ダイアログ ボックスで、をクリックして、**ラベルとコメント**タブ。  
  
2.  型、**ラベル**と**コメント**、 をクリックし、 **OK**。  
  
    > [!IMPORTANT]
    >  ラベルとコメントの functoid やリンクする方法の詳細については、次を参照してください。[リンクにラベルを付ける方法](../core/how-to-label-a-link.md)と[方法、Functoid ラベルとコメント](../core/how-to-label-and-comment-a-functoid.md)します。  
  
## <a name="see-also"></a>参照  
 [Functoid のプロパティおよび入力パラメーターの編集](../core/editing-functoid-properties-and-input-parameters.md)