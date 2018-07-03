---
title: 識別子の構成 (EDIFACT) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 097292f2-1aa5-42e4-aeee-c7d4cbdae17c
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c50743c237c66edcba1e6609dcd1ab9cb0081bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997219"
---
# <a name="configuring-identifiers-edifact"></a>識別子の構成 (EDIFACT)
未承認の受信者がインターチェンジを受信していないことを確認するには、パートナー アグリーメントで、受信者の参照パスワードを設定する必要があります。  
  
> [!IMPORTANT]
>  オフにした場合、このページで、次のプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。  
> 
> - **DestinationPartyName** **追加のアグリーメント リゾルバー**セクション。  
> 
>   プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-set-the-sender-recipient-and-recipient-password"></a>送信者、受信者、および受信者パスワードを設定するには  
  
1.  EDIFACT エンコード アグリーメントを」の説明に従って作成[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)します。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、**インターチェンジの設定**セクションで、**識別子**します。  
  
3.  **送信者 (UNB2)** セクションで、次の操作を行います。  
  
    1.  **Id (UNB2.1)**、1 つの最小値、35 文字の英数字を入力します。 このフィールドは必須です。  
  
    2.  **コードの修飾子 (UNB2.2)**、ドロップダウン リストから値を選択します。 このフィールドの入力は省略可能です。  
  
    3.  **逆ルーティングのアドレス (UNB2.3)**、1 つの文字の最小値、最大 14 文字の英数字を入力します。 このフィールドの入力は省略可能です。  
  
4.  **受信者 (UNB3)** セクションで、次の操作を行います。  
  
    1.  **Id (UNB3.1)**、1 つの最小値、35 文字の英数字を入力します。 このフィールドは必須です。  
  
    2.  **コードの修飾子 (UNB3.2)**、ドロップダウン リストから値を選択します。 このフィールドの入力は省略可能です。  
  
    3.  **逆ルーティングのアドレス (UNB3.3)**、1 つの文字の最小値、最大 14 文字の英数字を入力します。 このフィールドの入力は省略可能です。  
  
    4.  必要な場合、**受信者の参照パスワード (UNB6)** セクションで、受信者の参照パスワードの値を入力します。 **値 (UNB6.1)**、1 つの最小値、14 文字の英数字を入力します。 **修飾子 (UNB6.2)**、1 つの文字の最小値、最大 2 つの文字の英数字を入力します。 これらは省略可能なフィールドです。 これらの値が、受信したインターチェンジの "UNB6.1" フィールドおよび "UNB6.2" フィールドと一致しない場合、インターチェンジは中断されます。  
  
        > [!NOTE]
        >  組み合わせた**UNB6.1**と**UNB6.2**で一意である必要があります。  
  
        > [!NOTE]
        >  [UNB6.1] と [UNB6.2] の両方に値を入力し、変更を適用してから、[UNB6.1] の値を削除すると、[UNB6.2] の値も削除されて、このフィールドが無効になります。  
  
5.  **追加のアグリーメント リゾルバー**セクションの**DestinationPartyName**プロパティ、送信先パーティの値を指定します。 この値は、アグリーメントに対して送信メッセージを解決するためにも使用されます。 詳細については、「[アグリーメントの解決と送信 EDI メッセージのスキーマ決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)します。  
  
    > [!NOTE]
    >  通常必要はありませんを設定する、 **DestinationPartyName**プロパティ。 このプロパティは、アップグレード シナリオをサポートするアグリーメント プロパティの一部として使用できます。 BizTalk Server 2006 R2 または BizTalk Server 2009 からアップグレードするときに、 **DestinationPartyName**プロパティが BizTalk Server 2006 R2 または BizTalk Server 2009 のパーティの名前に設定します。  
  
6.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
    > [!IMPORTANT]
    >  クリックすると**OK**または**適用**この段階で、エラーが発生します。 UNB2 と UNB3 の値を提供する必要があるためにです、**識別子**他方の一方向アグリーメント タブのタブ。  
  
## <a name="see-also"></a>参照  
 [インターチェンジの設定の構成 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)