---
title: EDI パイプラインのプロパティの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edir2.edi.pipeline.properties
ms.assetid: 1b6229b6-a8b0-4824-86bd-39021844c5a8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c810b8507a98b91c0b906131e127f189f0a4fd0f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-edi-pipeline-properties"></a>EDI パイプラインのプロパティの構成
パイプラインのプロパティは、受信または送信 EDI インターチェンジの処理において、受信または送信インターチェンジを解決するアグリーメントを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が特定できない場合に使用されます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、パイプラインのプロパティを使用してインターチェンジを処理する場合があります。その他の場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ではフォールバック アグリーメントを使用します。 詳細については、次を参照してください。 [、EDI インターチェンジが構成されているの検証方法](../core/how-validation-of-an-edi-interchange-is-configured.md)です。  
  
 このルールにはいくつかの例外があります。  
  
-   X12 では、アグリーメントが特定された場合でも、実行時に使用される文字セットはパイプラインのプロパティによって決まります。 アグリーメントに記述されている文字セットは、アグリーメントのプロパティ設定を検証するためにのみ使用されます。  
  
-   EDIFACT では、受信インターチェンジに UNA セグメントがない場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は EfactDelimiters パイプライン プロパティで指定されている区切り記号を使用します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、メッセージが解決されるアグリーメントまたはフォールバック アグリーメントで定義されるプロパティは使用しません。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
## <a name="edi-pipeline-properties"></a>EDI パイプラインのプロパティ  
 EDI パイプラインでは、次のプロパティを設定できます。  
  
|プロパティ|新しく使用する機能|値|パイプライン - ステージ|  
|--------------|---------|------------|-----------------------|  
|AllowTrailingDelimiters|受信したインターチェンジに対して末尾の区切り記号を生成します。|False (既定値)<br /><br /> True|EdiReceive - 逆アセンブル<br /><br /> AS2EdiReceive - 逆アセンブル<br /><br /> EdiSend - アセンブル<br /><br /> AS2EdiSend - アセンブル|  
|CharacterSet|送信 EDI インターチェンジの実行時の検証中に使用する文字セットを指定します。<br /><br /> このプロパティは、X12 処理でのみ使用され、EDIFACT には使用されません。|UTF8 (既定値)<br /><br /> 基本<br /><br /> 拡張|EdiReceive - 逆アセンブル<br /><br /> AS2EdiReceive - 逆アセンブル<br /><br /> EdiSend - アセンブル<br /><br /> AS2EdiSend - アセンブル|  
|ConvertToImpliedDecimal|受信インターチェンジについて、BizTalk Server の中間 XML で、10 進形式 Nn で指定された EDI 番号を底 10 の数値に変換します。<br /><br /> このプロパティは、X12 処理でのみ使用され、EDIFACT には使用されません。|False (既定値)<br /><br /> True|EdiReceive - 逆アセンブル<br /><br /> AS2EdiReceive - 逆アセンブル|  
|CreateXMLTagForTrailingSeparators|末尾の区切り記号ごとに空の XML タグを作成 (設定した場合**AllowTrailingDelimiters** true)。|False (既定値)<br /><br /> True|EdiReceive - 逆アセンブル<br /><br /> AS2EdiReceive - 逆アセンブル|  
|DetectMID|単一のメッセージ内の複数のインターチェンジを EDI 逆アセンブラーで解析できるようにします。|True (既定値)<br /><br /> False|EdiReceive - 逆アセンブル<br /><br /> AS2EdiReceive - 逆アセンブル|  
|EdiDataValidation|フィールド長、省略可能性、および EDI データ要素の検証に加えて、繰り返し回数の検証を含む送信の EDI インターチェンジの EDI の種類 (データ要素) 検証を有効にします。|True (既定値)<br /><br /> False|EdiReceive - 逆アセンブル<br /><br /> AS2EdiReceive - 逆アセンブル<br /><br /> EdiSend - アセンブル<br /><br /> AS2EdiSend - アセンブル|  
|EfactDelimiters|受信インターチェンジの処理に使用される区切り記号を示します。 受信インターチェンジに UNA セグメントがない場合に使用されます。<br /><br /> 区切り記号には、次のものがあります。<br /><br /> UNA1 (合成データ要素区切り記号)<br />UNA2 (データ要素区切り記号)<br />UNA3 (小数点表記)<br />UNA4 (リリース インジケーター)<br />UNA5 (繰り返し区切り記号)<br />UNA6 (セグメント終端記号)**注:** edifact 処理にのみ、X12 ではなくこのプロパティを使用します。|0x3A、0x2B、0x2C、0x3F、0x20、0x27 (既定値)|EdiReceive - 逆アセンブル<br /><br /> AS2EdiReceive - 逆アセンブル|  
IgnoreMessageEncoding|BatchMarker コンポーネントが設定されていないこと、EDI を指定します。EncodingType コンテキスト プロパティを\<X12\>または\<EDIFACT\>です。 非 EDI メッセージを処理する際にカスタム パイプラインに適用されます。|False (既定値)<br /><br /> True|EdiReceive - パーティの解決<br /><br /> AS2EdiReceive - パーティの解決|  
|MaskSecurityInformation|情報の漏えいを防ぐために、受信 EDI インターチェンジのコンテキスト プロパティで認証/パスワードのセキュリティ情報をマスクします。 ISA1、ISA2、ISA3、ISA4 の各フィールド (X12 インターチェンジの場合)、および UNB6 フィールド (EDIFACT インターチェンジの場合) に適用されます。|True (既定値)<br /><br /> False|EdiReceive - 逆アセンブル<br /><br /> AS2EdiReceive - 逆アセンブル|  
|PreserveInterchange|受信したバッチを 1 つの単位として処理することを指定します。|False (既定値)<br /><br /> True|EdiReceive - 逆アセンブル<br /><br /> AS2EdiReceive - 逆アセンブル|  
|RouteAckOn2WayPort|双方向の要求 - 応答の受信ポートの開いている接続経由で EDI 受信確認を返します。|True (既定値)<br /><br /> False|EdiReceive - 逆アセンブル<br /><br /> AS2EdiReceive - 逆アセンブル|  
|UseDotAsDecimalSeperator|True に設定すると、EDI 受信パイプラインは 10 進数表記"です"。 受信ドキュメントの 10 進表記代わりにです。|False (既定値)<br /><br /> True|EdiReceive-逆アセンブル<br /><br /> AS2EdiReceive - 逆アセンブル|  
|UseIsa11AsRepetitionSeparator|繰り返し区切り文字として、標準識別子ではなく ISA11 が使用されることを指定します。 **注:** x12 処理でのみ、EDIFACT ではなくこのプロパティを使用します。|False (既定値)<br /><br /> True|EdiReceive - 逆アセンブル<br /><br /> AS2EdiReceive - 逆アセンブル|  
|XmlSchemaValidation|送信 EDI インターチェンジに対する拡張された (BTS-XSD) 検証を有効にします。 これは、データ型が EDI データ型ではない要素を使用してカスタマイズされたスキーマのみに適用されます。 これらの追加された要素は、EDI 検証では検証されないため、拡張された検証で検証されます。|False (既定値)<br /><br /> True|EdiReceive - 逆アセンブル<br /><br /> AS2EdiReceive - 逆アセンブル<br /><br /> EdiSend - アセンブル<br /><br /> AS2EdiSend - アセンブル|  
  
### <a name="to-set-a-pipeline-property"></a>パイプライン プロパティの設定  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、受信場所を右クリックするか送信ポートのプロパティを設定し、をクリックするパイプラインを使用して**プロパティ**です。  
  
2.  プロパティを設定する対象のパイプラインの横にある省略記号ボタン ([…]) をクリックします。  
  
3.  **パイプラインの構成**ダイアログ ボックスでは、プロパティの値を入力し、をクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [EDI インターチェンジの検証を構成する方法](../core/how-validation-of-an-edi-interchange-is-configured.md)