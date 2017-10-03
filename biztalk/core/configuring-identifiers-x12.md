---
title: "(X12) 識別子の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 665698d1-c46c-4149-9715-381b4966dd92
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4cbe3ce7badc9258e823034e5ed443d6f3d60e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-identifiers-x12"></a>識別子の構成 (X12)
パートナー アグリーメントでは、X12 を設定する必要があります未承認の受信者を承認およびセキュリティのプロパティによって、インターチェンジが受信していないことを確認するためにします。  
  
> [!NOTE]
>  ここで説明するインターチェンジ処理プロパティは、HIPAA インターチェンジにも当てはまります。  
  
> [!IMPORTANT]
>  オフにした場合、このページで、次のプロパティが無効、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。  
>   
>  -   **DestinationPartyName** **追加のアグリーメント リゾルバー**セクションです。  
>   
>  プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A、に対して、上記のプロパティの無効になりますで、**パーティ A にパーティ B]-> [**一方向アグリーメント タブです。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-set-sender-receiver-and-security-properties"></a>送信者、受信者、セキュリティのプロパティを設定するには  
  
1.  X12 エンコード アグリーメント」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)です。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブの下にある**インターチェンジの設定**セクションで、**識別子**です。  
  
3.  値を入力して、 **ISA1-2 (認証修飾子および認証情報)**です。 値を選択、**認証修飾子 (ISA1)**関連付けられているドロップダウン リストからです。 この値は、以外の場合**00**、用、**値 (ISA2)**テキスト ボックスに、1 つの英数字の最小値と最大 10 個を入力します。 このフィールドの入力は省略可能です。 これらの値を指定する場合は、受信したインターチェンジの ISA1 フィールドと ISA2 フィールドが一致するようにしてください。それ以外の場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はインターチェンジを中断します。  
  
4.  値を入力して、 **ISA3 4 (セキュリティ修飾子および認証情報)**です。 値を選択、**セキュリティ修飾子 (ISA3)**ドロップダウン リストからです。 この値は、以外の場合**00**、用、**値 (ISA4)**テキスト ボックスに、1 つの英数字値の最小値と最大 10 個を入力します。 このフィールドの入力は省略可能です。 これらの値が、受信したインターチェンジの ISA3 フィールドおよび ISA4 フィールドと一致しない場合、インターチェンジは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって中断されます。  
  
    > [!NOTE]
    >  値**03 – パスワード (下位互換用**が旧バージョンと互換性のために含まれる[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]し、将来のバージョンで削除される予定です。  
  
5.  値を入力します**(送信者の修飾子と識別子) の ISA5 ~ 6**です。 修飾子の値を選択、**送信者 Id 修飾子 (ISA5)**ドロップダウン リスト。 、識別子ので、**値 (ISA6)**テキスト ボックスに、1 つの英数字の最小値と最大 15 文字を入力します。  
  
6.  値を入力します**[isa7] ~ 8 (受信者の修飾子と識別子)**です。 修飾子の値を選択、**送信者 Id 修飾子 (ISA7)**ドロップダウン リスト。 、識別子ので、**値 (ISA8)**テキスト ボックスに、1 つの英数字の最小値と最大 15 文字を入力します。  
  
7.  **追加のアグリーメント リゾルバー**  セクションの**DestinationPartyName**プロパティ、送信先パーティの値を指定します。 この値は、アグリーメントに対して送信メッセージを解決するためにも使用されます。 詳細については、「[アグリーメントの解決と送信 EDI メッセージ スキーマの決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)です。  
  
    > [!NOTE]
    >  通常必要はありませんを設定する、 **DestinationPartyName**プロパティです。 このプロパティは、アップグレード シナリオをサポートするアグリーメント プロパティの一部として使用できます。 BizTalk Server 2006 R2 または BizTalk Server 2009 からアップグレードするときに、 **DestinationPartyName**プロパティが BizTalk Server 2006 R2 または BizTalk Server 2009 のパーティの名前に設定します。  
  
8.  をクリックして**適用**を変更を受け入れるか、をクリックして**OK**入力と、変更を検証し、ダイアログ ボックスを閉じます。  
  
    > [!IMPORTANT]
    >  クリックすると**OK**または**適用**この段階で、エラーが発生します。 ISA8 の値を ISA5 を提供する必要があるため、**識別子**他の一方向アグリーメント タブのタブ。  
  
## <a name="see-also"></a>参照  
 [(X12) インターチェンジの設定を構成します。](../core/configuring-interchange-settings-x12.md)