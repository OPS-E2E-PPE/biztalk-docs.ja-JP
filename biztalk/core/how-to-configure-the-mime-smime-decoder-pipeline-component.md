---
title: MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, attachments
- pipeline components, MIME/SMIME Decoder
- MIME/SMIME Decoder [pipeline component], configuring
- messages, verifying
- messages, decoding
- messages, digital signatures
- messages, security
ms.assetid: bfd44893-f1c3-4524-abc6-f820b8c0ef07
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a32137528de5ea18ea5698ab823c2e703651b71b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249722"
---
# <a name="how-to-configure-the-mime-smime-decoder-pipeline-component"></a>MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法
MIME/SMIME デコーダー パイプライン コンポーネントは、MIME/SMIME エンコードのメッセージをデコード/復号化したり、署名付きメッセージのデジタル署名を検証したりするときに使用されます。 外部の取引先と BizTalk Server との安全なドキュメント インターチェンジが必要な場合に、このコンポーネントが役立ちます。 このコンポーネントを使用して、添付ファイル付きのメッセージを受信することもできます。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の MIME/SMIME デコーダー パイプライン コンポーネントでは、ネイティブ 64 ビットをサポートしていません。  つまり、このコンポーネントは、32 ビットのエミュレーション モード プロセス (WOW64) で実行する必要があります。  このため、このデコーダー コンポーネント (または、元の受信パイプライン) を実行するホスト インスタンスは、32 ビットのエミュレーション モードで実行する必要があります。  このホスト インスタンスで BizTalk の他の要素を実行する場合、64 ビット サポートがないという制約がパフォーマンスなどに影響を与えることに注意してください。  
  
> [!NOTE]
>  MIME/SMIME デコーダー コンポーネントは、POP3 アダプター内でも使用されます。  そのため、POP3 アダプターが動作するホスト インスタンスには、同じネイティブ 64 ビット サポートの制約が存在します。  POP3 アダプターに関連する情報を参照してください[POP3 アダプター](../core/pop3-adapter.md)です。  
  
### <a name="to-configure-the-properties-for-the-mimesmime-decoder-pipeline-component"></a>MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成するには  
  
1.  MIME/SMIME デコーダー パイプライン コンポーネントを受信パイプラインのデコード ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**MIME 以外のメッセージを許可します。**|このプロパティを設定**True**かどうかが予想されること、受信パイプラインが MIME でエンコードされていないメッセージです。 このオプションは、異なる形式のメッセージ (たとえば、MIME エンコード メッセージやプレーン XML メッセージ) を受信するパイプラインで MIME/SMIME デコーダー パイプライン コンポーネントを使用する場合に役立ちます。 既定では、このプロパティに設定**False**、エンコードされた入力メッセージの意味は、コンポーネントは、非 MIME を受信した場合、エラーを生成します。 **注:** MIME デコーダーは、"Mime-version"ヘッダーを検索する受信メッセージの最初の 1024 バイトをスキャンします。 このヘッダーが見つからなかった場合、メッセージは非 MIME メッセージとして扱われます。 <br /><br /> 既定値: **False**|  
    |**ボディ パーツのコンテンツの種類**|MIME 部分のコンテンツの種類を示します。 このコンテンツの種類に該当する MIME 部分が BizTalk メッセージのボディ部になります。<br /><br /> 既定値: なし|  
    |**ボディ部のインデックス**|MIME 部分の一覧の 1 から始まるインデックスを示します。 一覧のこのインデックスにある MIME 部分が BizTalk メッセージのボディ部になります。 インデックスによるボディ部の選択を無効にするには、値を使用して**0**します。<br /><br /> 既定値: **0**|  
    |**失効確認一覧**|このプロパティを設定**True**送信者が BizTalk Server に送信されるメッセージに署名するのに使用する証明書に対して証明書失効リストを確認するかどうか。 このオプションを無効にすると、コンポーネントのパフォーマンスが向上します。<br /><br /> 証明書に関連付けられている証明書失効リストは、リモート Web サイト (Verisign.com など) からダウンロードされます。 BizTalk Server がこのリモート Web サイトに接続できなかった場合、そのメッセージはパイプラインを通過できません。<br /><br /> 既定値:**は True。**|  
  
## <a name="see-also"></a>参照  
 [MIME/SMIME デコーダー パイプライン コンポーネント](../core/mime-smime-decoder-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [MIME/SMIME プロパティ スキーマおよびプロパティ](../core/mime-smime-property-schema-and-properties.md)   
 [MIME (BizTalk Server サンプル)](../core/mime-biztalk-server-sample.md)