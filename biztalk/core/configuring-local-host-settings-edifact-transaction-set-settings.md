---
title: ローカル ホスト設定の構成 (EDIFACT トランザクション セットの設定) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f7c9cb9-7b4b-41de-a3f3-c0519b18673c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d918e422384a68875e2bf6625ca983c1819f1d61
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390927"
---
# <a name="configuring-local-host-settings-edifact-transaction-set-settings"></a>ローカル ホストの設定の構成 (EDIFACT トランザクション セットの設定)
受信インターチェンジを処理する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理およびインターチェンジの検証に使用する必要があるスキーマを決定する必要があります。 多数のドキュメント、スキーマに関連付けられたターゲット名前空間の決定し、使用するスキーマを決定します。 パーティ アグリーメントに関するこのページでは、ターゲット名前空間の決定に使用されるプロパティを入力します。 BizTalk Server が、スキーマを決定する方法が記載[アグリーメントの解決、スキーマ探索、および EDI メッセージの受信を承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)します。  
  
> [!IMPORTANT]
>  プロパティが無効になりません**パーティ A にパーティ B->** オフにした場合、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する** チェック ボックスパーティ A の同じページで、ただし、すべてのプロパティが無効に、**パーティ B には、パーティ A が->**  A を作成するときに、チェック ボックスを選択した場合のタブ  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
## <a name="determining-the-target-namespace"></a>Target Namespace を決定します。  
 **Target Namespace のカスタマイズ**グリッドで、Microsoft に付属する標準スキーマの名前空間のいずれかにターゲットの名前空間を設定することができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 値の関連付けるグリッドで、 **Target Namespace**要素の値、 **UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、 **UNG2.1**、および**UNG2.2**要素。 メッセージを受信した場合の**UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、 **UNG2.1**と**UNG2.2**要素に合わせて、グリッドの行で、BizTalk は対応する名前空間を使用してメッセージを処理するために使用するスキーマを決定します。 入力した要素の値は一意である必要があります。  
  
 メッセージとの一致を持たない場合、 **UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、 **UNG2.1**、**UNG2.2**グリッドで、BizTalk Server の行の各要素では、対象の行の名前空間を使用してメッセージを処理します。、**既定**列がチェックされます。 既定のターゲット名前空間として機能します。 BizTalk での既定の名前空間を使用して名前空間が識別されない場合`http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006`します。  
  
> [!NOTE]
>  グリッドで、フィールドのいずれかの設定を入力し、その設定を削除して場合、は、行全体を削除する必要がありますか、ページが検証に失敗します。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>トランザクション セットのローカル ホスト設定を構成するには  
  
1.  EDIFACT エンコード アグリーメントを」の説明に従って作成[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)します。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、**トランザクション セットの設定**セクションで、**ローカル ホスト設定**します。  
  
3.  トランザクションの一部が設定した場合、検証の設定をセットとして**末尾の区切り記号のポリシー**に **(省略可能)** または**必須**を選択できます**空アイテムの作成末尾の区切り記号に XML タグを**がインターチェンジの送信者が末尾の区切り記号に空の XML タグが含まれます。  
  
4.  選択**小数点区切り文字として使用してドット (.)** を有効にする BizTalk Server では、10 進数を含むインターチェンジから作成された XML メッセージにドット (.) を含めます。  
  
5.  **Target Namespace のカスタマイズ**セクションで、次の操作を行います。  
  
    1.  選択、**既定**を定義する既定のターゲット名前空間を含む行のチェック ボックス。  
  
    2.  **UNH2.1**列、メッセージの種類を指定します。 (最大で 6 文字)。  
  
    3.  **UNH2.2**列、メッセージのバージョン番号を指定します。 最低限、1 つの文字 (最大 3 つの文字)。  
  
    4.  **UNH2.3**列、メッセージ リリース番号を指定します。 最低限、1 つの文字 (最大 3 つの文字)。  
  
    5.  **UNH2.5**列で、割り当てコードを指定します。 (最大 6 文字です。 必要があります英数字を入力します。  
  
    6.  **UNG2.1**列で、アプリケーション送信者 id を 1 つの文字、最大 35 文字の最小の英数字を入力します。 このフィールドが必要です。  
  
    7.  **UNG2.2**列で、アプリケーション送信者コードの修飾子を 1 つの文字の最小値、最大 4 つの文字の英数字を入力します。 このフィールドは省略可能です。  
  
    8.  **Target Namespace**列で、ドロップダウン リストから選択するか、グリッドの行のデータ要素と、インターチェンジのフィールドの間で一致が見つからない場合は、インターチェンジに使用するターゲットの名前空間を入力します。  
  
        > [!NOTE]
        >  これらの値は、いる BizTalk Server が受信したインターチェンジに関連付けられた値と比較されます。  
  
    9. 使用するその他のターゲット名前空間は、この手順を繰り返します。  
  
    10. 一覧からターゲットの名前空間を削除する行を選択し、をクリックして**削除**します。  
  
6.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [トランザクション セットの設定を構成する (EDIFACT)](../core/configuring-transaction-set-settings-edifact.md)