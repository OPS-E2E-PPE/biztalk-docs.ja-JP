---
title: MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法 |Microsoft Docs
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
ms.openlocfilehash: cde85adeec5d1155afdba28d2e7ca2bf5647983d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386024"
---
# <a name="how-to-configure-the-mime-smime-decoder-pipeline-component"></a>MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法
MIME/SMIME デコーダー パイプライン コンポーネントは、デコードとエンコードされた MIME/SMIME メッセージを復号化と署名付きメッセージのデジタル署名を検証するために使用されます。 このコンポーネントは、外部のパートナーと BizTalk Server の間にセキュリティで保護されたドキュメントのインターチェンジが必要な場合に便利です。 このコンポーネントは、添付ファイル付きメッセージを受信するためも使用できます。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、MIME/SMIME デコーダー パイプライン コンポーネントには、ネイティブの 64 ビット サポートはありません。  つまり、このコンポーネントは、32 ビットのエミュレーション モード プロセス (WOW64) で実行する必要があります。  つまり、32 ビットのエミュレーション モードでこのデコーダー コンポーネント (または一部をそれが受信パイプライン) を実行するホスト インスタンスを実行する必要があります。  このホスト インスタンスで BizTalk の他の要素を実行する場合、64 ビット サポートがないという制約がパフォーマンスなどに影響を与えることに注意してください。  
> 
> [!NOTE]
>  MIME/SMIME デコーダー コンポーネントは、POP3 アダプター内でも使用されます。  その結果、POP3 アダプターを実行するホスト インスタンスのネイティブの 64 ビット サポートにも同じ制限が存在します。  POP3 アダプターに関する関連情報を参照してください。 [POP3 アダプター](../core/pop3-adapter.md)します。  
  
### <a name="to-configure-the-properties-for-the-mimesmime-decoder-pipeline-component"></a>MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成するには  
  
1.  MIME/SMIME デコーダー パイプライン コンポーネントを受信パイプラインのデコード ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**MIME 以外のメッセージを許可します。**|このプロパティを設定**True**期待するかどうかは、受信パイプラインが MIME でエンコードされていないメッセージを取得できます。 このオプションは、さまざまな形式、たとえば、MIME エンコードやプレーン XML メッセージを受信するパイプラインで MIME/SMIME デコーダー パイプライン コンポーネントを使用する場合に便利です。 既定では、このプロパティに設定**False**、エンコードされた入力メッセージを MIME 以外を受信した場合、コンポーネントはエラーを生成します。 意味します。 **注:** MIME デコーダーは、"Mime-version"ヘッダーを検索する受信メッセージの先頭の 1024 バイトをスキャンします。 このヘッダーが見つからない場合、メッセージは非 MIME メッセージとして扱われます。 <br /><br /> 既定値:**False**|  
    |**ボディ部のコンテンツの種類**|MIME 部分のコンテンツの種類を示します。 このコンテンツの種類の MIME 部分には、BizTalk メッセージのボディ部になります。<br /><br /> 既定値:なし|  
    |**ボディ部のインデックス**|MIME 部分の一覧に 1 から始まるインデックスを示します。 このインデックスの一覧である MIME 部分には、BizTalk メッセージのボディ部になります。 インデックスによるボディ部の選択を無効にするには、値を使用して**0**します。<br /><br /> 既定値:**0**|  
    |**失効確認一覧**|このプロパティを設定**True**送信者が BizTalk Server に送信されるメッセージに署名するのに使用される証明書の証明書失効リストを確認したいかどうか。 このオプションを無効にすると、コンポーネントのパフォーマンスが向上します。<br /><br /> 証明書に関連付けられている証明書失効リストは、リモートの Web サイト (Verisign.com など) からダウンロードされます。 BizTalk Server がリモートの Web サイトに接続できない場合は、パイプラインでメッセージが失敗します。<br /><br /> 既定値:**True**|  
  
## <a name="see-also"></a>参照  
 [MIME/SMIME デコーダー パイプライン コンポーネント](../core/mime-smime-decoder-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [MIME-SMIME プロパティ スキーマおよびプロパティ](../core/mime-smime-property-schema-and-properties.md)   
 [MIME (BizTalk Server サンプル)](../core/mime-biztalk-server-sample.md)