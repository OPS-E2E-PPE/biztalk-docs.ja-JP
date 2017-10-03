---
title: "ローカル ホスト設定の構成 (EDIFACT トランザクション セットの設定) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f7c9cb9-7b4b-41de-a3f3-c0519b18673c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 912af3a047f77f077bf9de58a25802f3c658e6b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-local-host-settings-edifact-transaction-set-settings"></a>ローカル ホストの設定の構成 (EDIFACT トランザクション セットの設定)
受信したインターチェンジを処理するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はインターチェンジの処理および検証に使用するスキーマを決定する必要があります。 この場合、スキーマに関連付けられたターゲット名前空間および使用するスキーマを決定します。 パーティ アグリーメントに関するこのページで、ターゲット名前空間の決定に使用するプロパティを入力します。 BizTalk Server が、スキーマを決定する方法が説明されている[アグリーメントの解決、スキーマ探索、および受信した EDI メッセージの承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)です。  
  
> [!IMPORTANT]
>  プロパティが無効**パーティ A にパーティ B->** をオフにした場合は、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する** チェック ボックスパーティ A の同じ ページで、ただし、すべてのプロパティが無効にします**パーティ B には、パーティ A が->**   タブの A の作成中に、チェック ボックスを選択した場合  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
## <a name="determining-the-target-namespace"></a>ターゲットの名前空間の決定  
 **カスタマイズ Target Namespace**グリッドで、Microsoft に付属する標準スキーマ用の名前空間のいずれかにターゲットの名前空間を設定することができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 グリッド内の値を関連付ける、 **Target Namespace**要素の値を**UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、 **UNG2.1**、および**UNG2.2**要素。 BizTalk がメッセージを受信するときに持つ**UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、 **UNG2.1**、および**UNG2.2**要素にグリッドの行に合わせて、BizTalk は対応する名前空間を使用してメッセージを処理するために使用するスキーマを決定します。 入力する要素の値は一意である必要があります。  
  
 メッセージとの一致にいない場合、 **UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、 **UNG2.1**、**UNG2.2**グリッドでは、BizTalk Server の行の各要素は対象の行に、名前空間を使用してメッセージを処理、**既定**列を選択します。 それが既定のターゲットの名前空間として機能します。 名前空間が識別されない場合は、`http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006` の既定のターゲットの名前空間が使用されます。  
  
> [!NOTE]
>  グリッド内のいずれかのフィールドに設定を入力した後、その設定を削除する場合は、行全体を削除する必要があります。行全体を削除しないと、ページの検証に失敗します。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>トランザクション セットのローカル ホスト設定を構成するには  
  
1.  EDIFACT」の説明に従ってエンコード アグリーメントを作成する[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)です。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブの下にある**トランザクション セットの設定**セクションで、**ローカル ホストの設定**です。  
  
3.  トランザクションの一部が設定した場合、検証の設定をセットとして**末尾の区切り記号のポリシー**に**オプション**または**必須**を選択できます**空を作成末尾の区切り記号のタグで XML**して、インターチェンジの送信者が末尾の区切り記号に空の XML タグが含まれます。  
  
4.  選択**小数点区切り文字として使用してドット (.)**できるようにする BizTalk Server では、10 進数を含むインターチェンジから作成された XML メッセージにドット (.) を含めます。  
  
5.  **カスタマイズ Target Namespace**セクションで、次の操作します。  
  
    1.  選択、**既定**を定義する既定のターゲット名前空間を含む行のチェック ボックスです。  
  
    2.  **UNH2.1**列で、メッセージの種類を指定します。 最大文字数は 6 文字)。  
  
    3.  **UNH2.2**列で、メッセージのバージョン番号を指定します。 (最低限、1 つの文字以外の場合は最大文字数は 3 つの文字)。  
  
    4.  **UNH2.3**列で、メッセージのリリース番号を指定します。 (最低限、1 つの文字以外の場合は最大文字数は 3 つの文字)。  
  
    5.  **UNH2.5**列で、割り当てコードを指定します。 (最大 6 文字です。 英数字である必要があります)。  
  
    6.  **UNG2.1**列で、英数字の値の 1 つの文字および 35 文字の最大数を最小限に抑えてアプリケーション送信者 id を入力します。 このフィールドが必要です。  
  
    7.  **UNG2.2**列で、アプリケーション送信者コードの修飾子を 1 つの文字の最小値、最大 4 文字の英数字を入力します。 このフィールドは省略可能です。  
  
    8.  **Target Namespace**列で、ドロップダウン リストから選択するか、グリッドのどの行のデータ要素と、インターチェンジ内のフィールドの間で一致が検出されないときに、インターチェンジに対して使用されるターゲットの名前空間を入力します。  
  
        > [!NOTE]
        >  これらの値は、BizTalk Server が受信したインターチェンジに関連付けられている値と比較されます。  
  
    9. 使用するその他のターゲットの名前空間に対して、これらの手順を繰り返します。  
  
    10. 一覧からターゲットの名前空間を削除する行を選択し、をクリックして**削除**です。  
  
6.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [トランザクション セットの構成設定 (EDIFACT)](../core/configuring-transaction-set-settings-edifact.md)