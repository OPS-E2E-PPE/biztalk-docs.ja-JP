---
title: バッチの管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82755840-4e00-4fed-80e0-1a22b248c0bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4903cf2722f1938ceb1df92c2a3ac2a88fe6d61e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263490"
---
# <a name="managing-batches"></a>バッチの管理
リリースを手動で制御する方法の上部にあるコントロールを使用して、インターチェンジをバッチ処理、**バッチ構成**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス (で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール) X12 と EDIFACT エンコードの両方にします。 この作業には、次の制御が含まれます。  
  
-   **バッチの開始**です。 バッチ処理オーケストレーションのインスタンスをアクティブにします。 選択した後、**開始** ボタン、バッチ処理要素インスタンスがアクティベーションの範囲内にある場合に収集されます。  
  
-   **バッチの上書き**です。 既存の要素を使用してバッチを作成し、即座に送信します。 バッチの送信後、バッチ処理オーケストレーションは、確立された設定に基づいてバッチ処理を再開します。  
  
-   **バッチの停止**です。 バッチ処理オーケストレーションのアクティブなインスタンスを非アクティブ化します。 選択した後、**停止**ボタン、オーケストレーション既存のバッチ要素からバッチを作成する場合、インターチェンジを EDI 送信パイプラインに配信し、終了します。  
  
 これらの制御は単一のバッチ構成に対して実行されます。  
  
 キーを押したときに BizTalk が、アクション、**開始**ボタンによって異なります、**フィルター**条件、**リリース**条件、および**アクティベーション**範囲の設定、**バッチ構成**ページ。 フィルター条件によって、バッチ処理の対象となるメッセージが決まります。 バッチがリリースされたときに、リリース条件を決定します。 アクティベーションの範囲のプロパティによって、バッチ処理オーケストレーションのアクティブなインスタンスがバッチ処理要素を収集するかどうかが決まります。 これらの設定の詳細については、次を参照してください。[送信バッチの構成](../core/configuring-an-outgoing-batch.md)です。  

このトピックでは、開始、停止、上書き、およびバッチを削除する方法を示します。  

> [!NOTE]
>  バッチを構成する方法については、次を参照してください。[構成 X12 バッチ処理](../core/configuring-batching-x12.md)または[EDIFACT バッチ処理の構成](../core/configuring-batching-edifact.md)です。 
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
> [!NOTE]
>  メンバー、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループが開始、停止、またはバッチの上書きが構成のバッチ処理に関連の設定を変更することはできません。 バッチ構成を変更するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーである必要があります。  
  
## <a name="start-stop-and-override-batches"></a>開始、停止、およびバッチの上書き  
  
1.  開いている**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**BizTalk グループを展開し、選択、**パーティ**です。  
  
2.  **パーティとビジネス プロファイル**] ページの [、**契約**セクションで、開始、停止、または上書きするバッチの構成とのアグリーメントを右クリックします。  
  
3.  一方向アグリーメント タブで、**アグリーメントのプロパティ**、select、**バッチ構成**ページ。  
  
4.  **バッチ構成** ページで、開始、停止、または上書きするバッチのタブを選択します。  
  
5.  フィルター条件、リリース条件、およびアクティベーションの範囲のプロパティが正しく設定されていることを確認します。  
  
    > [!NOTE]
    >  メンバーである場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]演算子グループはなく、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループ、起動、停止、または上書きをバッチ処理します。 しかし、バッチの構成設定を変更することはできません。 設定が、設定を変更する場合は、使用する表示され を選択**OK**、アクセス許可エラーが発生しました。  
  
6.  バッチ処理オーケストレーションのインスタンスがアクティブ化されていない場合は、選択**開始**インスタンスをアクティブにします。  
  
    > [!NOTE]
    >  - バッチ処理オーケストレーションのインスタンスがアクティブになっていないことがわかります、**開始**ボタンが有効になっていると**バッチ処理がアクティブ化されていない**だけ下に表示される、 **の開始**コントロール。  
    >  - クリックした場合、**開始** ボタン、バッチ処理オーケストレーションのインスタンスがアクティブ化されてが要素が、バッチの収集されないことを確認の datetime、**アクティベーション**テキスト ボックスが経過しました。 ない場合、**アクティベーション**を現在の日付または過去の日付を設定する必要があります。  
  
7.  リリース条件が満たされていないときに、バッチ インターチェンジを送信する選択**オーバーライド**です。  
  
    > [!NOTE]
    >  選択すると**オーバーライド**送信されるバッチ インターチェンジになります。 ただし、バッチ処理オーケストレーション インスタンスや、アクティベーション条件、リリース条件のライセンス認証の状態には影響しません。  
  
8.  バッチ処理オーケストレーションのインスタンスを非アクティブ化するには選択**停止**です。  
  
    > [!NOTE]
    >  選択すると**停止**に送信されるバッチ インターチェンジとバッチ処理オーケストレーションのインスタンスが終了します。  
  
9. 選択**OK**または**キャンセル**を閉じる、**アグリーメントのプロパティ**です。  

## <a name="delete-batches"></a>バッチを削除します。  
  
1.   **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理****パーティ**です。  
  
2.  **パーティとビジネス プロファイル**] ページの [、**契約**セクションで、削除するバッチの構成とのアグリーメントを右クリックします。  
  
3.  一方向アグリーメント タブで、**アグリーメントのプロパティ**ダイアログ ボックスで、**バッチ構成**ページ。  
  
4.  **バッチ構成** ページで、削除するバッチのタブを選択します。  
  
5.  タブ ページの右隅にある、次のように選択します。**削除**です。  
  
6.  選択**OK**を閉じる、**アグリーメントのプロパティ**です。  

  
## <a name="see-also"></a>参照  
 [送信バッチの構成](../core/configuring-an-outgoing-batch.md)  
 [EDI および AS2 ソリューションの管理](../core/managing-edi-and-as2-solutions.md)