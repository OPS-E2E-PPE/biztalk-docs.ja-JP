---
title: MIME/SMIME デコーダー パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, MIME/SMIME Decoder
- MIME/SMIME Decoder [pipeline component]
ms.assetid: ff6c963c-1b5c-4be4-9eef-3ec9a018e7fd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 593873b1d3252eed752de21fe4bb9c99dc664974
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394479"
---
# <a name="mime-smime-decoder-pipeline-component"></a>MIME/SMIME デコーダー パイプライン コンポーネント
MIME/SMIME デコーダー コンポーネントは、MIME デコードのメッセージの機能を提供します。 このパイプライン コンポーネントは、受信パイプラインのデコード ステージに配置できる 7 bit、8 bit、binary、引用符で囲まれた印刷可能な UUEncode、および base64 デコードをサポートしています。 ローカライズされたデータの文字セットの変更では、デコードすることは変わりません。  
  
 MIME/SMIME デコーダー コンポーネントは、復号化し、受信メッセージの署名検証できます。 サービスが実行されている現在のユーザーの個人証明書ストアから暗号化解除証明書が使用されます。 ローカル コンピューターのアドレス帳ストアまたはメッセージ自体から、署名検証証明書が使用されます。  
  
 成功したメッセージの暗号化の解除、MIME/SMIME デコーダー パイプライン コンポーネントは、メッセージの述語としてメッセージを復号化するために使用する暗号化解除証明書の拇印を関連付けます。 これは、そのメッセージをサブスクライブしている任意のサービス (オーケストレーションまたは送信ポート) がそのキーを所有しているホストを関連付ける必要があることを意味します。 ホストとキー間の関連付けは、ホストのプロパティとして、BizTalk 管理コンソールで完了できます。 BizTalk 管理コンソールで、ホストを構成する方法の詳細については、次を参照してください。[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)します。  
  
 MIME/SMIME デコーダー パイプライン コンポーネントは、のみ-、-インボックス マルチパート MIME/SMIME メッセージなどのマルチパート メッセージを処理するパイプライン コンポーネントを受信します。 パイプライン コンポーネントは、メッセージを解析し、同等のマルチパート BizTalk メッセージを作成します。 マルチパート BizTalk メッセージが、ボディ部という 1 つの一意の部分です。 すべての他のパイプライン コンポーネントなど、XML 逆アセンブラー パイプライン コンポーネントは、BizTalk メッセージのボディ部を処理するだけです。 また、BizTalk ボディ部に対応する MessageType をサブスクライバーにメッセージをルーティングに使用されます。  
  
 マルチパート MIME メッセージに対応する BizTalk BodyPart を識別するために、MIME/SMIME デコーダー パイプライン コンポーネントでは、次の条件が評価されます。 条件の評価の順序は次のとおりです。  
  
1.  Content-description ヘッダーが"body"(大文字) に設定する最初の MIME/SMIME 部分。  
  
2.  最初の MIME/SMIME 部分を"text/xml"(case-insensitive) に設定されたコンテンツ タイプ ヘッダーを持ちます。  
  
3.  設定コンテンツ タイプ ヘッダーを持つ最初の MIME/SMIME 部分"text/"(大文字)。  
  
4.  最初の MIME/SMIME 部分。  
  
> [!NOTE]
>  順序の出力の部分の BizTalk メッセージが MIME/SMIME メッセージの MIME/SMIME 部分の順序と同じです。  
  
> [!NOTE]
>  マルチパート BizTalk メッセージの中の場合はサブスクライブまたはオーケストレーションによって使用される、メッセージ内の部分の数が、オーケストレーションをアクティブにするメッセージの部分の数と一致します。  
  
 MIME/SMIME デコーダー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)します。 BizTalk Server のサポートの復号化、署名認証、証明書の利用状況の詳細については、次を参照してください。[送信と受信メッセージのセキュリティ](../core/security-for-sending-and-receiving-messages.md)します。  
  
## <a name="see-also"></a>参照  
 [パイプライン コンポーネント](../core/pipeline-components.md)   
 [MIME-SMIME プロパティ スキーマおよびプロパティ](../core/mime-smime-property-schema-and-properties.md)   
 [MIME (BizTalk Server サンプル)](../core/mime-biztalk-server-sample.md)