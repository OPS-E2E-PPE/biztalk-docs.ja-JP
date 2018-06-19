---
title: ローカル ホスト設定 (X12 トランザクション セットの設定) の構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 8fcc099535e6a7b96c5c4bbdd29112da46af3522
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234306"
---
# <a name="configuring-local-host-settings-x12-transaction-set-settings"></a>ローカル ホスト設定の構成 (X12 トランザクション セットの設定)
受信したインターチェンジを処理するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はインターチェンジの処理および検証に使用するスキーマを決定する必要があります。 この場合、スキーマに関連付けられたターゲット名前空間および使用するスキーマを決定します。 パーティ アグリーメントに関するこのページで、ターゲット名前空間の決定に使用するプロパティを入力します。 どの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]スキーマについては、「を決定[アグリーメントの解決、スキーマ探索、および受信した EDI メッセージの承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)です。  
  
> [!NOTE]
>  このトピックは、HIPAA 関連の設定にも当てはまります。  
  
> [!IMPORTANT]
>  プロパティが無効**パーティ A にパーティ B->** をオフにした場合は、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する** チェック ボックスパーティ A の同じ ページで、ただし、すべてのプロパティが無効にします**パーティ B には、パーティ A が->**   タブの A の作成中に、チェック ボックスを選択した場合  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
## <a name="determining-the-target-namespace"></a>ターゲットの名前空間の決定  
 **をカスタマイズするターゲットの名前空間**グリッド、用に設定できるターゲットの名前空間、名前空間のいずれかに付属の標準スキーマ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 グリッドの値を関連付ける、 **Target Namespace**アプリケーション送信者の値を持つ要素 (**GS2**) およびトランザクション セット識別コード (**ST1**)。 BizTalk がメッセージを受信すると持つ**GS2**と**ST1**データ要素に合わせて、グリッドの行で、メッセージの処理に対応する名前空間が使用されます。 入力する要素の値は一意である必要があります。  
  
 メッセージとの一致にいない場合、 **GS2**と**ST1**グリッドでは、BizTalk Server の任意の行のデータ要素は対象の行に、名前空間を使用してメッセージを処理、 **を既定値**列を選択します。 それが既定のターゲットの名前空間として機能します。 名前空間が指定されていない場合、BizTalk Server は `http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006` の既定の名前空間を使用します。  
  
> [!NOTE]
>  グリッド内のいずれかのフィールドに設定を入力した後、その設定を削除する場合は、行全体を削除する必要があります。行全体を削除しないと、ページの検証に失敗します。  
  
> [!NOTE]
>  このグリッドの使用方法については、EDI インターフェイス開発チュートリアルで、インターチェンジの送信側パーティの設定に関する説明を参照してください。 詳細については、次を参照してください。[手順 4:、取引先のパーティとビジネス プロファイルを構成する](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)です。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>トランザクション セットのローカル ホスト設定を構成するには  
  
1.  X12 エンコード アグリーメント」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)です。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブの下にある**トランザクション セットの設定**セクションで、**ローカル ホストの設定**です。  
  
3.  選択**暗黙的な 10 進形式 Nn を底 10 の数値を変換**に BizTalk Server での中間 XML で底 10 の数値に形式 Nn で指定された EDI 番号を変換します。  
  
    > [!NOTE]
    >  この変換の後、中間 XML は長さの検証でエラーになる可能性があります。 これは、底 10 の数値形式の番号に 10 進数が含まれるために発生するもので、その番号の長さは Nn 形式の番号より 1 だけ大きくなります。 この問題を解決するにはの値を追加して**1**最小値/最大長の値にします。  
  
4.  トランザクションの一部が設定した場合、検証の設定をセットとして**末尾の区切り記号のポリシー**に**オプション**または**必須**を選択できます**空を作成末尾の区切り記号のタグで XML**して、インターチェンジの送信者が末尾の区切り記号に空の XML タグが含まれます。  
  
5.  **カスタマイズ Target Namespace**セクションで、次の操作します。  
  
    1.  選択、**既定**を定義する既定のターゲット名前空間を含む行のチェック ボックスです。  
  
    2.  **St1 の場合**ドロップダウン リストからセット識別コードを列で、トランザクションの値を選択します。  
  
    3.  **GS2**列で、アプリケーション送信者に 2 つの文字の最小値と最大 15 文字の英数字の値を入力します。 このフィールドは必須です。  
  
    4.  **Target Namespace**列で、ドロップダウン リストから選択するか、グリッドのどの行のデータ要素と、インターチェンジ内のフィールドの間で一致が検出されないときに、インターチェンジに対して使用されるターゲットの名前空間を入力します。  
  
        > [!NOTE]
        >  これらの値は、BizTalk Server が受信したインターチェンジに関連付けられている値と比較されます。  
  
    5.  使用するその他のターゲットの名前空間に対して、これらの手順を繰り返します。  
  
    6.  一覧からターゲットの名前空間を削除する行を選択し、をクリックして**削除**です。  
  
6.  をクリックして**適用**を変更を受け入れるか、をクリックして**OK**入力と、変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [トランザクション セットの構成設定 (X12)](../core/configuring-transaction-set-settings-x12.md)