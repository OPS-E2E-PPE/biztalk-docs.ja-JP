---
title: ローカル ホスト設定 (X12 トランザクション セットの設定) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e31b41c3-49fc-46ef-ab69-889e30dfc58e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 897a8f5c9cacd84f8a54f06276c0170fba7045cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390840"
---
# <a name="configuring-local-host-settings-x12-transaction-set-settings"></a>ローカル ホスト設定の構成 (X12 トランザクション セットの設定)
受信インターチェンジを処理する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理およびインターチェンジの検証に使用する必要があるスキーマを決定する必要があります。 多数のドキュメント、スキーマに関連付けられたターゲット名前空間の決定し、使用するスキーマを決定します。 パーティ アグリーメントに関するこのページでは、ターゲット名前空間の決定に使用されるプロパティを入力します。 どの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]決定スキーマについては、「[アグリーメントの解決、スキーマ探索、および EDI メッセージの受信を承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)します。  
  
> [!NOTE]
>  このトピックでは、HIPAA 関連の設定にも適用されます。  
  
> [!IMPORTANT]
>  プロパティが無効になりません**パーティ A にパーティ B-> **オフにした場合、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する** チェック ボックスパーティ A の同じページで、ただし、すべてのプロパティが無効に、**パーティ B には、パーティ A が-> ** A を作成するときに、チェック ボックスを選択した場合のタブ  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
## <a name="determining-the-target-namespace"></a>Target Namespace を決定します。  
 **カスタマイズのターゲットの名前空間**グリッド用に設定できるターゲットの名前空間、名前空間のいずれかに付属の標準スキーマ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 値の関連付けるグリッドで、 **Target Namespace**アプリケーション送信者の値を持つ要素 (**GS2**) およびトランザクション セット識別コード (**ST1**)。 メッセージを受信した場合の**GS2**と**ST1**データ要素に合わせて、グリッドの行で、メッセージの処理に対応する名前空間が使用されます。 入力した要素の値は一意である必要があります。  
  
 メッセージとの一致を持たない場合、 **GS2**と**ST1**グリッドで、BizTalk Server の任意の行のデータ要素は対象の行で、名前空間を使用して、メッセージを処理、 **を既定値**列がチェックされます。 既定のターゲット名前空間として機能します。 BizTalk Server での既定の名前空間を使用して名前空間が識別されない場合`http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006`します。  
  
> [!NOTE]
>  グリッドで、フィールドのいずれかの設定を入力し、その設定を削除して場合、は、行全体を削除する必要がありますか、ページが検証に失敗します。  
  
> [!NOTE]
>  このグリッドを使用しての図解は、EDI インターフェイス開発チュートリアルでは、具体的からインターチェンジを受信するパーティの設定を実行します。 詳細については、次を参照してください。[手順 4。取引先のパーティとビジネス プロファイルを構成する](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)します。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>トランザクション セットのローカル ホスト設定を構成するには  
  
1.  X12 エンコード アグリーメントを」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)します。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、**トランザクション セットの設定**セクションで、**ローカル ホスト設定**します。  
  
3.  選択**変換には 10 進形式 Nn を底 10 の数値が含まれる**を BizTalk Server での中間 XML で底 10 の数値形式 Nn で指定されている EDI 番号を変換します。  
  
    > [!NOTE]
    >  この変換後の中間 XML に長さの検証は失敗します。 これは、底 10 の数値書式の数値は、Nn 形式で、長さ、数より大きい値のいずれかを行う、10 進数を含まれているために発生します。 値を追加することで、この問題を解決できます**1**最小値/最大長の値にします。  
  
4.  トランザクションの一部が設定した場合、検証の設定をセットとして**末尾の区切り記号のポリシー**に **(省略可能)** または**必須**を選択できます**空アイテムの作成末尾の区切り記号に XML タグを**がインターチェンジの送信者が末尾の区切り記号に空の XML タグが含まれます。  
  
5.  **Target Namespace のカスタマイズ**セクションで、次の操作を行います。  
  
    1.  選択、**既定**を定義する既定のターゲット名前空間を含む行のチェック ボックス。  
  
    2.  **St1 の場合**列では、トランザクションの値を選択しますが、ドロップダウン リストから識別子コードを設定します。  
  
    3.  **GS2**列、2 つの文字の最小値、最大 15 文字のアプリケーション送信者の英数字を入力します。 このフィールドは必須です。  
  
    4.  **Target Namespace**列で、ドロップダウン リストから選択するか、グリッドの行のデータ要素と、インターチェンジのフィールドの間で一致が見つからない場合は、インターチェンジに使用するターゲットの名前空間を入力します。  
  
        > [!NOTE]
        >  これらの値は、いる BizTalk Server が受信したインターチェンジに関連付けられた値と比較されます。  
  
    5.  使用するその他のターゲット名前空間は、この手順を繰り返します。  
  
    6.  一覧からターゲットの名前空間を削除する行を選択し、をクリックして**削除**します。  
  
6.  をクリックして**適用**を変更を受け入れるか、をクリックする**OK**を入力し、変更を検証して、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [トランザクション セットの設定の構成 (X12)](../core/configuring-transaction-set-settings-x12.md)