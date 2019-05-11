---
title: アグリーメントの解決、スキーマ探索、および受信した EDI メッセージの承認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 503e307c-4cb0-49b5-8751-82dcea203151
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e82722ddb6adfcd3e0f8c5d24050bb58471da378
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359645"
---
# <a name="agreement-resolution-schema-discovery-and-authorization-for-received-edi-messages"></a>アグリーメントの解決、スキーマ探索、および受信した EDI メッセージの承認
ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI メッセージを受信、EDI 受信パイプラインが取引先アグリーメント解決、スキーマ探索、およびメッセージを処理する方法を決定する承認プロセスを実行します。  
  
## <a name="agreement-resolution"></a>アグリーメントの解決  
 EDI 受信パイプラインは、一連のメッセージのヘッダー フィールドとプロパティでアグリーメント定義間の一致があるかどうかを判断する手順を実行することによって取引先パートナー アグリーメントの解決を実行します。 1 回[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アグリーメントが決定されます (下記参照) のインターチェンジに適用されるドキュメント スキーマを決定します。 一致するアグリーメントと関連するスキーマに関連付けられたプロパティを検証および受信したメッセージの処理に使用します。  
  
 アグリーメントの解決を実行する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次のように進みます。  
  
1. 送信者の修飾子と識別子、および受信者の修飾子および識別子をインターチェンジ ヘッダーとアグリーメントのプロパティを照合してアグリーメントを解決します。  
  
2. 手順 1. が成功しなかった場合は、送信者の修飾子と、インターチェンジ ヘッダーとアグリーメントのプロパティでの識別子だけを照合することで、アグリーメントを解決します。 また、最初のステップが成功しなかったためがあると想定しても安全[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージを受信します。 そのため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信者の修飾子と識別子を次の一致を試みます。  
  
   -   値"BT"および"HostX12Recvr"(X12 でエンコードされたメッセージ) と  
  
   -   値"BT"および"HostEdifactRecvr"(EDIFACT でエンコードされたメッセージ)  
  
   > [!IMPORTANT]
   > - **BizTalk Server 2013 R2、2013、および 2010**:ISA5、ISA6、ISA7、ISA8、UNB2.1、UNB2.2、UNB3.1、および [unb3.2] フィールドでは、アグリーメントの設定で必須です。  
   >   -   **BizTalk Server 2009 および 2006 R2**:ISA7、ISA8、UNB3.1、および [unb3.2] フィールドは、パーティ設定で必須ではありません。 フィールドは空白の場合、EDI エンジンは ISA5、ISA6、UNB2.1、UNB2.2 の値に基づいて解決を提供します。  
   >   -   BizTalk Server 2009 および 2006 R2 から BizTalk Server の新しいバージョンに解像度をサポートするために、ハード コードされた Id (HostX12Recvr および HostEdifactRecvr) と修飾子 (BT) が導入されています。  
   >   -   EDIFACT メッセージが従う必要があります、 [UNECE ガイドライン](http://www.unece.org/tradewelcome/areas-of-work/un-centre-for-trade-facilitation-and-e-business-uncefact/outputs/standards/unedifact/tradeedifactrules.html)メッセージの構文と規則。  
  
3. 手順 2. が成功しなかった場合は、フォールバック アグリーメントのプロパティを使用します。  
  
   X12 の場合、最初の手順で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を照合に次の値が使用されます。  
  
- ISA05 (送信者の修飾子)  
  
- ISA06 (送信者 id)  
  
- ISA07 (受信者の修飾子)  
  
- ISA08 (受信者 id)  
  
  Edifact では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を照合に次の値が使用されます。  
  
- UNB2.1 (送信者 id)  
  
- UNB2.2 (送信者の修飾子)  
  
- UNB3.1 (受信者 id)  
  
- UNB3.2 (受信者の修飾子)  
  
  照合に使用されるアグリーメントのプロパティが定義されている、**識別子**の特定方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
  これら 4 つの受信側と送信側のプロパティは、取引先アグリーメントを一意に識別します。 4 つのプロパティを使用してより柔軟で受信側の処理。 などのアグリーメントの解決には、このメソッドでは、送信ポートを複数作成することがなく複数のパーティに対する受信確認を送信する有効可能性があります。  
  
  場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]すべてを使用してアグリーメントを解決できない送信者と受信者の修飾子と識別子を 4 つにするは、送信者の修飾子と識別子だけを使用してアグリーメントを解決を試みます。 これらのフィールドは ISA05 と ISA06; x12 の場合edifact では、これらのフィールドは、UNB2.1 および UNB2.2 は。 送信者と受信者のプロパティと一致すると同様[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インターチェンジ ヘッダーの値と一致するアグリーメントのプロパティで定義されている、**識別子**の特定方向アグリーメントタブのページ**アグリーメントのプロパティ** ダイアログ ボックス。 送信者の修飾子と識別子を使用して、アグリーメントを解決するには、専用の場合、受信者の修飾子と識別子は未定義になって、双方向アグリーメント タブの**アグリーメントのプロパティ** ダイアログ ボックス。  
  
  アグリーメントが見つからない場合、し[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポート設定は認証を必要としない限り、フォールバックのパートナー アグリーメントを取引先を使用します。 ポートの設定には、認証が必要な場合 (いずれか**認証が失敗した場合は、メッセージを削除**または**認証が失敗した場合は、メッセージを保持する**で選択した、**全般**ページ、**受信ポートのプロパティ**)、アグリーメントが、受信ポートで受信したインターチェンジ必要です。 この場合、インターチェンジ ヘッダーとアグリーメントのプロパティを照合してアグリーメントが解決しない場合、フォールバック アグリーメントのプロパティを使用してアグリーメントを特定はできません。 インターチェンジはアグリーメントが見つからない場合、認証に失敗したかのように処理されは中断されます。  
  
> [!NOTE]
>  EDI パイプライン内のメッセージは次の手順にアグリーメントで解決、メッセージがアグリーメントを持つ有効な状態の手順に解決されるまでします。 たとえば場合は、メッセージがアグリーメントの解決の最初の手順で解決を取得しますが、アグリーメントが無効の状態が次の解決手順をメッセージが通過します。  
  
## <a name="schema-discovery"></a>スキーマの検出  
 後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]スキーマの検証およびメッセージを処理するために使用する必要がありますを決定する必要があります、メッセージに解決されるアグリーメントが決定されます。 指定されたプロパティを使用して、**ローカル ホストの設定**ページ (送信側) の一方向のアグリーメント タブの**アグリーメントのプロパティ** ダイアログ ボックス。  
  
 スキーマを決定する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]スキーマ名前空間を決定する必要がありますまずします。 付属の標準スキーマ用、EDI 逆アセンブラーに既定の名前空間を使用するか[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、またはカスタム スキーマを使用する名前空間を決定します。  
  
 **ローカル ホスト設定**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックスでは、カスタムの名前空間を決定する値のグリッドを設定することができます。 EDI 逆アセンブラーで既定の名前空間を使用してそのグリッドで一致するものがない場合、**ターゲットの名前空間**フィールドは、既定の行をマークします。  
  
### <a name="x12-schema-discovery"></a>X12 スキーマ探索  
 X12 エンコード メッセージのため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション送信者の識別子 (GS02) と、トランザクションを使用して、カスタムの名前空間受信したインターチェンジのヘッダーからの ID (ST01) の設定を判断します。 内の GS02] と [ST01 プロパティのこれらの値と値の間の一致を確認しようと、**ターゲットの名前空間をカスタマイズ**でグリッド、**ローカル ホストの設定**ページ ([**トランザクションセットの設定**) の双方向アグリーメント タブの**アグリーメントのプロパティ**] ダイアログ ボックス。 一致が見つかると、スキーマを検証し、メッセージの処理を決定するのにグリッドの同じ行で指定されたターゲットの名前空間が使用されます。 ターゲットの名前空間が決定されない場合は、既定のターゲット名前空間が使用されます。 名前空間が指定されていない場合、**ターゲットの名前空間**フィールドが設定されていますが、既定の行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は、既定では、X12でエンコードされたメッセージのフォールバックアグリーメントプロパティで識別されるターゲットの名前空間を使用`http://schemas.microsoft.com/BizTalk/Edi/X12/2006`.  
  
 X12 インターチェンジの場合、ターゲットの名前空間が検出されると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の情報を使用してスキーマを決定します。  
  
- 検出されたターゲットの名前空間  
  
- ST03 の最初の 5 文字のバージョン/リリース (場合 GS07 Accredited Standards Committee X12 X を = =)。 バージョンの GS08 または ISA12 の最初の 5 文字が続くかどうかは、ST03 が存在する/無効なまたはスキーマの解決が行われません (場合 GS07! = X)。  
  
- ST01 の DocType  
  
  EDI 逆アセンブラーは、エンコードの種類、バージョン/リリース、および"X12_00401_864"など、スキーマ名を確認する DocType を連結します。 次に連結しますターゲットの名前空間とスキーマ名では、たとえば、`http://schemas.microsoft.com/BizTalk/Edi/X12/2006/X12#X12_00401_864`します。  
  
  受信した HIPAA 837 インターチェンジ、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 3 つの HIPAA 837 スキーマをサポートしています。  
  
|837 スキーマ|バージョン 4010 GS08 の値|バージョン 5010 の GS08/ST03 の値|  
|----------------|--------------------------------|--------------------------------------|  
|Claim-dental_837d|004010X097A1|005010X224A1|  
|Claim-institutional_837i|004010X096A1|005010X223A1|  
|Claim-professional_837p|004010X098A1|005010X222|  
  
> [!NOTE]
>  トランザクション セット 278 (Health Care Services Review) に対して、HIPAA バージョンでは、要求と応答の両方のペアは、GS08 および ST01 の同じ値を共有します。 BHT02 のフィールドを 278 とを区別することがあります内のトリガー値に応じて要求/応答バージョン 5010 で。  
> 
> 1. Health Care Services Review Request 01、13、36 bht02 の値のいずれかを示します  
>    2.  bht02 11 は、Health Care Services Review Response をことを示します  
  
### <a name="edifact-schema-discovery"></a>EDIFACT スキーマ探索  
 EDIFACT でエンコードされたメッセージでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージの種類 (UNH2.1)、メッセージのバージョン番号 (UNH2.2)、割り当てコード (UNH2.5)、メッセージ リリース番号 (UNH2.3) を使用してカスタムの名前空間を決定します機能グループ ID (UNG2.1)、およびアプリケーション送信コード。受信したインターチェンジのヘッダーからの修飾子 (UNG2.2)。 UNH2.1、UNH2.2、UNH2.3、UNH2.5、UNG2.1、および UNG2.2 のプロパティの値とこれらの値の検索を試みます、**ターゲットの名前空間のカスタマイズ**グリッド ([**トランザクション セットの設定**)双方向アグリーメント タブの**アグリーメントのプロパティ**] ダイアログ ボックス。 一致が見つかると、検証およびメッセージの処理に使用するのにスキーマを決定するのにグリッドの同じ行で指定されたターゲットの名前空間が使用されます。 ターゲットの名前空間が決定されない場合は、既定のターゲット名前空間が使用されます。 名前空間が指定されていない場合、**ターゲットの名前空間**フィールドが設定されていますが、既定の行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ターゲットの名前空間、EDIFACT でエンコードされたメッセージをフォールバック アグリーメント プロパティで指定された既定を使用`http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006`.  
  
 EDIFACT インターチェンジの場合、ターゲットの名前空間が検出されると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の情報を使用してスキーマを決定します。  
  
- 検出されたターゲット名前空間。  
  
- UNH2.2 のメッセージのバージョン番号。  
  
- UNH2.3 のメッセージ リリース番号。  
  
- メッセージの種類 (unh2.1)。  
  
- 割り当てコード (unh2.5)。  
  
  EDI 逆アセンブラーは、エンコードの種類、バージョン、リリース、およびスキーマ名を確認するメッセージ型"EFACT_D94A_CONTEN"を連結します。 次に連結しますターゲットの名前空間とスキーマ名では、たとえば、`http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006/EFACT#EFACT_D94A_CONTEN`します。  
  
  UNH2.5 がメッセージに存在する場合は、EDI 逆アセンブラーは最初にスキーマ名、たとえば"EFACT_D94A_CONTEN_TEST"の一部として UNH2.5 の値を使用して、一致するスキーマを検索しようとします。 一致するスキーマが見つからない場合、EDI 逆アセンブラーがフォールバック UNH2.5 の値のないスキーマを検索します。  
  
## <a name="authorization"></a>Authorization  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージのフィールドとのアグリーメントに対して定義された承認およびセキュリティ フィールドの値を確認します。 一致しない場合がある場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インターチェンジは中断されます。 EDIFACT でエンコードされたメッセージでは、これらのフィールドは受信者の参照パスワード (UNB6.1 および UNB6.2 です)。 X12 でエンコードされたメッセージでは、これらのフィールドは、認証修飾子と情報 (ISA1 ~ 2) とセキュリティ修飾子 (ISA3 ~ 4) の情報。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が EDI メッセージを受信する方法](../core/how-biztalk-server-receives-edi-messages.md)