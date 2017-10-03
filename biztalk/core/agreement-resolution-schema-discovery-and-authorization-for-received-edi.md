---
title: "アグリーメントの解決、スキーマ探索、および受信した EDI メッセージの承認 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 503e307c-4cb0-49b5-8751-82dcea203151
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de5f7fd9b022daf2d123de1c971797b53df202d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="agreement-resolution-schema-discovery-and-authorization-for-received-edi-messages"></a>受信した EDI メッセージのアグリーメントの解決、スキーマ探索、および認証
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が EDI メッセージを受信すると、そのメッセージの処理方法を決定するために、EDI 受信パイプラインによって取引先アグリーメント解決、スキーマ探索、および認証のプロセスが実行されます。  
  
## <a name="agreement-resolution"></a>アグリーメント解決  
 EDI 受信パイプラインによって実行される取引先アグリーメント解決とは、メッセージのヘッダー フィールドに一致するプロパティを持つアグリーメント定義を見つけるための一連の手順を実行することです。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によってアグリーメントが特定されると、次に、そのインターチェンジに適用されるドキュメント スキーマが特定されます (後述)。 一致するアグリーメントに関連付けられたプロパティおよび関連するスキーマを使用して、受信したメッセージが検証され、処理されます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がアグリーメント解決を実行する手順は、次のとおりです。  
  
1.  アグリーメントを解決するために、インターチェンジ ヘッダーの中の送信者の修飾子と識別子および受信者の修飾子と識別子をアグリーメントのプロパティと照合して、一致するアグリーメントを見つけます。  
  
2.  手順 1. で一致するものが見つからない場合は、インターチェンジ ヘッダーの中の送信者の修飾子と識別子だけをアグリーメントのプロパティと照合して、一致するアグリーメントを見つけます。 この時点では、最初の手順で一致するものが見つかっていないので、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がメッセージを受信することになっていると考えることができます。 したがって、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、受信者の修飾子および識別子が以下の値に一致するものを見つけます。  
  
    -   値 "BT" および "HostX12Recvr" (X12 でエンコードされたメッセージの場合)  
  
    -   値 "BT" および "HostEdifactRecvr" (EDIFACT でエンコードされたメッセージの場合)  
  
    > [!IMPORTANT]
    >  -   **BizTalk Server 2013 R2、2013、および 2010**: ISA5、ISA6、ISA7、ISA8、UNB2.1、UNB2.2、UNB3.1、および unb3.2 フィールドには、アグリーメント設定で必須です。  
    > -   **BizTalk Server 2009 および 2006 R2**:、ISA7、ISA8、UNB3.1、および [unb3.2] フィールドは、パーティ設定で必須ではありません。 これらのフィールドを空白のままにすると、EDI エンジンでは ISA5、ISA6、UNB2.1、UNB2.2 の値に基づいて解決が実行されます。  
    > -   BizTalk Server 2009 および BizTalk Server 2006 R2 以降のバージョンによる解決をサポートするために、ハード コードされた ID (HostX12Recvr および HostEdifactRecvr) と修飾子 (BT) が導入されています。  
    > -   EDIFACT メッセージが従う必要があります、 [UNECE ガイドライン](http://www.unece.org/tradewelcome/areas-of-work/un-centre-for-trade-facilitation-and-e-business-uncefact/outputs/standards/unedifact/tradeedifactrules.html)メッセージの構文と規則にします。  
  
3.  手順 2. で一致するものが見つからない場合は、フォールバック アグリーメントのプロパティを使用します。  
  
 最初の手順で、X12 の場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は以下の値を照合に使用します。  
  
-   ISA05 (送信者の修飾子)  
  
-   ISA06 (送信者の識別子)  
  
-   ISA07 (受信者の修飾子)  
  
-   ISA08 (受信者の識別子)  
  
 EDIFACT の場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は以下の値を照合に使用します。  
  
-   UNB2.1 (送信者の識別子)  
  
-   UNB2.2 (送信者の修飾子)  
  
-   UNB3.1 (受信者の識別子)  
  
-   UNB3.2 (受信者の修飾子)  
  
 一致するために使用するアグリーメントのプロパティが定義されている、**識別子**の特定方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
 この 4 つの受信側と送信側のプロパティによって、取引先アグリーメントが一意に識別されます。 4 つのプロパティを使用することで、受信側の処理の柔軟性が向上します。 たとえば、このアグリーメント解決方法ならば、受信確認の送信先のパーティが複数の場合も、送信ポートを複数作成する必要はありません。  
  
 送信者と受信者の修飾子と識別子の 4 つすべてを使用してもアグリーメントを解決できない場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は送信者の修飾子と識別子のみを使用してアグリーメントの解決を試みます。 X12 の場合のこれらのフィールドは、ISA05 と ISA06 です。EDIFACT の場合は、UNB2.1 と UNB2.2 です。 送信者と受信者のプロパティの照合と同様[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インターチェンジ ヘッダーの値と一致するアグリーメントのプロパティで定義されている、**識別子**の特定方向アグリーメントタブのページ**アグリーメントのプロパティ** ダイアログ ボックス。 だけの場合、送信者の修飾子と識別子は、アグリーメントを解決するのには、受信者の修飾子と識別子は未定義になって、双方向アグリーメント タブの**アグリーメントのプロパティ** ダイアログ ボックス。  
  
 アグリーメントが 1 つも見つからない場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はフォールバック取引先アグリーメントを使用します (認証を必要とするようにポートが設定されている場合を除く)。 ポートの設定は、認証を必要とする場合 (いずれか**認証が失敗した場合は、メッセージをドロップ**または**認証が失敗した場合は、メッセージを保持する**で選択した、**全般**ページの**受信ポートのプロパティ**)、アグリーメントは、受信ポートで受信したインターチェンジに必要です。 この場合は、インターチェンジ ヘッダーとアグリーメント プロパティの照合によるアグリーメント解決が不可能ならば、フォールバック アグリーメント プロパティを使用してアグリーメントを特定することは許可されません。 アグリーメントが見つからない場合は、インターチェンジは認証に失敗したものと見なされて、中断状態となります。  
  
> [!NOTE]
>  EDI パイプライン内のメッセージは、有効な状態のアグリーメントに解決されるまで、アグリーメント解決における次の手順に進みます。 たとえば、メッセージがアグリーメント解決の最初の手順で解決されたとしても、アグリーメントが無効な状態の場合、メッセージは次の解決手順に進みます。  
  
## <a name="schema-discovery"></a>スキーマ探索  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、解決を実行してメッセージからアグリーメントを特定したら、次にこのメッセージの検証および処理にどのスキーマを使用するかを決定します。 指定されたプロパティを使用して、**ローカル ホスト設定**一方向 (送信側) のページのアグリーメント タブの**アグリーメントのプロパティ** ダイアログ ボックス。  
  
 スキーマを決定するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で初めにスキーマの名前空間を決定する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 付属の標準スキーマに対しては既定の名前空間が使用され、カスタム スキーマに対しては、どの名前空間を使用するかを EDI 逆アセンブラーが決定します。  
  
 **ローカル ホスト設定**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックスでは、カスタム名前空間を決定する値のグリッドを設定することができます。 EDI 逆アセンブラーで既定の名前空間を使用してそのグリッドで一致が見つからない場合、**ターゲットの名前空間**フィールドは、既定の行の対象としてマークします。  
  
### <a name="x12-schema-discovery"></a>X12 スキーマ探索  
 X12 でエンコードされたメッセージの場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では受信したインターチェンジのヘッダーのアプリケーション送信者識別子 (GS02) とトランザクション セット ID (ST01) を使用して、カスタム名前空間が決定されます。 内の GS02 および ST01 プロパティのこれらの値と値の間の一致を検索しようと、**ターゲットの名前空間をカスタマイズ**グリッドで、**ローカル ホストの設定**ページ ([**トランザクションセットの設定**) の双方向アグリーメント タブの**アグリーメントのプロパティ**] ダイアログ ボックス。 一致が見つかると、スキーマを検証し、メッセージを処理するのにことを決定するのにグリッドの同じ行で指定されたターゲットの名前空間が使用されます。 ターゲットの名前空間が決定されない場合は、既定のターゲットの名前空間が使用されます。 名前空間が指定されていない場合、**ターゲットの名前空間**、既定の行のマークされたフィールド[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は、既定でX12エンコードメッセージの場合、フォールバックアグリーメントプロパティで指定されたターゲットの名前空間を使用`http://schemas.microsoft.com/BizTalk/Edi/X12/2006`.  
  
 X12 インターチェンジの場合、ターゲットの名前空間が検出されると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では次の情報を使用してスキーマが決定されます。  
  
-   検出されたターゲットの名前空間  
  
-   ST03 の最初の 5 文字のバージョン/リリース (GS07 == X - Accredited Standards Committee X12 の場合)。 ST03 が存在しないか無効である場合、またはスキーマを決定できない場合は、GS08 または ISA12 (GS07 != X の場合) の最初の 5 文字でバージョンが決定されます。  
  
-   ST01 の DocType  
  
 EDI 逆アセンブラーは、エンコードの種類、バージョン/リリース、および DocType を連結して、スキーマ名 ("X12_00401_864" など) を決定します。 次に、ターゲットの名前空間とスキーマ名を連結します (例: `http://schemas.microsoft.com/BizTalk/Edi/X12/2006/X12#X12_00401_864`)。  
  
 受信した HIPAA 837 インターチェンジの場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では 3 つの HIPAA 837 スキーマをサポートします。  
  
|837 スキーマ|GS08 の値 (Version 4010)|GS08/ST03 の値 (Version 5010)|  
|----------------|--------------------------------|--------------------------------------|  
|Claim-Dental_837D|004010X097A1|005010X224A1|  
|Claim-Institutional_837I|004010X096A1|005010X223A1|  
|Claim-Professional_837P|004010X098A1|005010X222|  
  
> [!NOTE]
>  HIPAA の各バージョンのトランザクション セット 278 (Health Care Services Review) については、GS08 および ST01 の値は要求と応答のどちらのペアも同じです。 BHT02 フィールド、278 とを区別することがあります内のトリガー値に応じて要求/応答バージョン 5010 で。  
>   
>  1.  BHT02 の値が 01、13、36 のいずれかならば、Health Care Services Review Request  
> 2.  BHT02 が 11 ならば、Health Care Services Review Response  
  
### <a name="edifact-schema-discovery"></a>EDIFACT スキーマ探索  
 EDIFACT でエンコードされたメッセージの場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では受信したインターチェンジのヘッダーからメッセージの種類 (UNH2.1)、メッセージのバージョン番号 (UNH2.2)、メッセージのリリース番号 (UNH2.3)、割り当てコード (UNH2.5)、機能グループ ID (UNG2.1)、およびアプリケーション送信コードの修飾子 (UNG2.2) を使用して、カスタムの名前空間が決定されます。 内の UNH2.1、UNH2.2、UNH2.3、UNH2.5、UNG2.1、および ung2.2 の各プロパティのこれらの値と値の間の一致を検索を試みます、**ターゲットの名前空間をカスタマイズ**グリッド ([**トランザクション セットの設定**)双方向アグリーメント タブの**アグリーメントのプロパティ**] ダイアログ ボックス。 一致するものが見つかった場合は、グリッドの同じ行で指定されたターゲットの名前空間が使用されて、メッセージの検証および処理のためのスキーマが決定されます。 ターゲットの名前空間が決定されない場合は、既定のターゲットの名前空間が使用されます。 名前空間が指定されていない場合、**ターゲットの名前空間**、既定の行のマークされたフィールド[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ターゲットの名前空間、EDIFACT でエンコードされたメッセージのフォールバック アグリーメント プロパティで指定した既定を使用`http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006`.  
  
 EDIFACT インターチェンジの場合、ターゲットの名前空間が検出されると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では次の情報を使用してスキーマが決定されます。  
  
-   検出されたターゲットの名前空間。  
  
-   メッセージ バージョン番号 (UNH2.2)。  
  
-   メッセージ リリース番号 (UNH2.3)。  
  
-   メッセージの種類 (UNH2.1)。  
  
-   割り当てコード (UNH2.5)。  
  
 EDI 逆アセンブラーは、エンコードの種類、バージョン、リリース、およびメッセージの種類を連結して、スキーマ名 ("EFACT_D94A_CONTEN" など) を決定します。 次に、ターゲットの名前空間とスキーマ名を連結します (例: `http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006/EFACT#EFACT_D94A_CONTEN`)。  
  
 メッセージ内に UNH2.5 が存在する場合は、UNH2.5 の値が名前に含まれるスキーマ (たとえば "EFACT_D94A_CONTEN_TEST") の検出が試行されます。 一致するスキーマが見つからない場合は、UNH2.5 の値を使用せずにスキーマの検出が試行されます。  
  
## <a name="authorization"></a>承認  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、アグリーメントに対して定義されている認証およびセキュリティのフィールドの値と、メッセージのフィールドを比較します。 一致しない場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はインターチェンジを中断します。 EDIFACT エンコード メッセージの場合のこれらのフィールドは、受信者の参照パスワード (UNB6.1 および UNB6.2) です。 X12 エンコード メッセージの場合のこれらのフィールドは、認証修飾子および認証情報 ([ISA1] ～ [ISA2]) とセキュリティ修飾子およびセキュリティ情報 ([ISA3] ～ [ISA4]) です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が EDI メッセージを受信する方法](../core/how-biztalk-server-receives-edi-messages.md)