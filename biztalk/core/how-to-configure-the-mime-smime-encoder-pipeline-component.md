---
title: MIME-SMIME エンコーダー パイプライン コンポーネントを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, encrypting digital signatures
- pipeline components, MIME/SMIME Encoder
- Partner Management, security
- MIME/SMIME Encoder [pipeline component], configuring
- messages, encoding
- messages, multi-parts
ms.assetid: dcbb08e8-d300-4e7f-9c1c-907fb602e721
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b0dbe61e79ba569313d3bccbbbbfdf053835042
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991067"
---
# <a name="how-to-configure-the-mime-smime-encoder-pipeline-component"></a>MIME-SMIME エンコーダー パイプライン コンポーネントを構成する方法
MIME/SMIME エンコーダー パイプライン コンポーネントを使用して、送信メッセージのエンコードおよび暗号化を行い、送信メッセージに署名します。 BizTalk Server と外部の取引先との安全なドキュメント インターチェンジが必要な場合に、このコンポーネントが役立ちます。 また、このコンポーネントを使用して、BizTalk Server マルチパート メッセージを送信できます。  

> [!NOTE]
>  BizTalk 2006 の MIME/SMIME エンコーダー パイプライン コンポーネントでは、ネイティブ 64 ビットをサポートしていません。  つまり、このコンポーネントは、32 ビットのエミュレーション モード プロセス (WOW64) で実行する必要があります。  このため、このエンコーダー コンポーネント (または、元の送信パイプライン) を実行するホスト インスタンスは、32 ビットのエミュレーション モードで実行する必要があります。  このホスト インスタンスで BizTalk の他の要素を実行する場合、64 ビット サポートがないという制約がパフォーマンスなどに影響を与えることに注意してください。  

### <a name="to-configure-the-properties-for-the-mimesmime-encoder-pipeline-component"></a>MIME/SMIME エンコーダー パイプライン コンポーネントのプロパティを構成するには  

1. MIME/SMIME エンコーダー パイプライン コンポーネントを送信パイプラインのエンコード ステージにドラッグします。  

2. [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。  


   |             プロパティ             |                                                                                                                                                                                                                                                                                                                              目的                                                                                                                                                                                                                                                                                                                               |
   |----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **メッセージに署名証明書を追加します。**  |                                                                                                                                                                                                                    場合、**署名の種類**プロパティは**NoSign**を設定して、署名付きメッセージに署名証明書を追加するかどうかを選択することができます、**メッセージに署名 Cert の追加**プロパティ。<br /><br /> 既定値:**は True。**                                                                                                                                                                                                                     |
   |    **失効確認一覧**     |                                                                                                                                                                                                                                                                   SMIME メッセージの処理中に、証明書失効リストを確認するかどうかを指定します。<br /><br /> 既定値:**は True。**                                                                                                                                                                                                                                                                    |
   |  **コンテンツ転送エンコード**   |                                                                                                                                                                                                                                                     エンコード形式を示します。<br /><br /> オプション : Base64、QuotedPrintable、SevenBit、EightBit、Binary、および UUEncode。<br /><br /> 既定値: **Base64**                                                                                                                                                                                                                                                      |
   |      **暗号化を有効にします。**       |                                                                                                                                     設定**True**送信メッセージを暗号化する場合。 このオプションが有効になっている場合、ユーザーが設定して使用する暗号化アルゴリズムを選択できる、**暗号化アルゴリズム**プロパティ。 MIME/SMIME エンコーダー パイプライン コンポーネントでは、メッセージの暗号化に BizTalk エクスプローラーの送信ポートと関連付けられている公開キー証明書が使用されます。<br /><br /> 既定値: **False**                                                                                                                                     |
   |     **暗号化アルゴリズム**     |                                                                            暗号化アルゴリズムを定義します。<br /><br /> このプロパティは、場合にのみ設定できます**暗号化を有効にする**に設定されている**True**します。<br /><br />**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]以降のバージョン**、AES 暗号化が自動的に含まれます。 オプションがあります: AES128、DES3、DES、RC2 (既定値)、AES192、AES256 です。<br /><br />以前[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョンでは、オプションがあります: DES3 (既定)、DES、RC2。                                                                             |
   | **添付ファイルとしてボディ部を送信します。** |                                                                                                                                        設定**True**を BizTalk メッセージのボディ部を MIME 添付ファイルとして送信する場合。<br /><br /> 既定値: **False** **重要:** にこのプロパティを設定する必要がありますいない**True** BizTalk サーバー間でメッセージを送信するときにします。 設定した場合、受信側でメッセージが 2 つの部分メッセージとして解釈されるため、メッセージのデコード処理で、カスタム コードが必要になります。                                                                                                                                        |
   |        **署名の種類**        | 送信メッセージに署名する場合は、このプロパティで署名の形式を選択します。 このプロパティには、次の 3 つの値があります。<br /><br /> -   **NoSign**します。 メッセージは署名されません。<br />-   **ClearSign**します。 メッセージに署名が追加されます。 **ClearSign**場合に使用することはできません**暗号化を有効にする**に設定されている**True**します。<br />-   **[Blobsign]** します。 メッセージに署名が付けられ、メッセージはエンコードされます。<br /><br /> MIME/SMIME エンコーダー コンポーネントでは、メッセージの署名に、BizTalk 管理コンソールの BizTalk グループに関連付けられている秘密キーのクライアント証明書が使用されます。<br /><br /> 既定値: **NoSign** |

   MIME 添付ファイルのファイル名を設定するには、使用、 **FileName**プロパティ、**システム**メッセージ部分の名前空間。  

## <a name="see-also"></a>参照  
 [MIME-SMIME エンコーダー パイプライン コンポーネント](../core/mime-smime-encoder-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [MIME-SMIME プロパティ スキーマおよびプロパティ](../core/mime-smime-property-schema-and-properties.md)   
 [MIME (BizTalk Server サンプル)](../core/mime-biztalk-server-sample.md)