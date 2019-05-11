---
title: (X12) 識別子の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 665698d1-c46c-4149-9715-381b4966dd92
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 603c7d2f27dc350f269942e3303d4eeebf26cb1e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355412"
---
# <a name="configuring-identifiers-x12"></a>識別子の構成 (X12)
パートナー アグリーメントでは、X12 を設定する必要がありますが、インターチェンジを受信しないことを確認するために承認およびセキュリティのプロパティの未承認の受信者。  
  
> [!NOTE]
>  ここで説明するインターチェンジ処理プロパティは、HIPAA インターチェンジにも適用されます。  
> 
> [!IMPORTANT]
>  オフにした場合、このページで、次のプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。  
> 
> - **DestinationPartyName** **追加のアグリーメント リゾルバー**セクション。  
> 
>   プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-set-sender-receiver-and-security-properties"></a>送信者、受信者、およびセキュリティのプロパティを設定するには  
  
1. X12 エンコード アグリーメントを」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)します。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2. 一方向アグリーメント タブで、**インターチェンジの設定**セクションで、**識別子**します。  
  
3. 値を入力、 **ISA1 2 (認証修飾子およびセキュリティ情報)** します。 値を選択、**認証修飾子 (ISA1)** 関連付けられているドロップダウン リストから。 この値は、以外の場合**00**の**値 (ISA2)** テキスト ボックスに、1 文字の英数字の最小値と最大 10 個を入力します。 これは、オプションのフィールドです。 これらの値を指定すると場合、それ以外の場合、受信したインターチェンジの ISA1、ISA2 フィールドと一致する確認[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インターチェンジは中断されます。  
  
4. 値を入力、 **ISA3 ~ 4 (セキュリティ修飾子およびセキュリティ情報)** します。 値を選択、**セキュリティ修飾子 (ISA3)** ドロップダウン リストから。 この値は、以外の場合**00**、用、**値 (ISA4)** テキスト ボックスに、1 つの英数字値の最小値、最大 10 個を入力します。 これは、オプションのフィールドです。 これらの値には、受信したインターチェンジの ISA3 と ISA4 フィールドが一致しない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インターチェンジは中断されます。  
  
   > [!NOTE]
   >  値**03 – パスワード (旧バージョンとの互換性) 用**、旧バージョンと互換性のために含まれる[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]は将来のバージョンで削除されます。  
  
5. 値を入力**ISA5 ~ 6 (送信者の修飾子と識別子)** します。 修飾子の値を選択、**送信者 Id 修飾子 (ISA5)** ドロップダウン リスト。 識別子についての**値 (ISA6)** テキスト ボックスに、1 文字の英数字の最小値と最大 15 文字を入力します。  
  
6. 値を入力 **[isa7] ~ 8 (受信者の修飾子と識別子)** します。 修飾子の値を選択、**送信者 Id 修飾子 (ISA7)** ドロップダウン リスト。 識別子についての**値 (ISA8)** テキスト ボックスに、1 文字の英数字の最小値と最大 15 文字を入力します。  
  
7. **追加のアグリーメント リゾルバー**セクションの**DestinationPartyName**プロパティ、送信先パーティの値を指定します。 この値は、送信メッセージをアグリーメントに解決するのにも使用されます。 詳細については、「[アグリーメントの解決と送信 EDI メッセージのスキーマ決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)します。  
  
   > [!NOTE]
   >  通常必要はありませんを設定する、 **DestinationPartyName**プロパティ。 このプロパティは、使用可能なアップグレード シナリオをサポートするために、アグリーメント プロパティの一部として。 BizTalk Server 2006 R2 または BizTalk Server 2009 からアップグレードするときに、 **DestinationPartyName**プロパティが BizTalk Server 2006 R2 または BizTalk Server 2009 のパーティの名前に設定します。  
  
8. をクリックして**適用**を変更を受け入れるか、をクリックする**OK**を入力し、変更を検証して、ダイアログ ボックスを閉じます。  
  
   > [!IMPORTANT]
   >  クリックすると**OK**または**適用**この段階で、エラーが発生します。 ISA8 の値に ISA5 を提供する必要があるためにです、**識別子**他方の一方向アグリーメント タブのタブ。  
  
## <a name="see-also"></a>参照  
 [インターチェンジの設定の構成 (X12)](../core/configuring-interchange-settings-x12.md)