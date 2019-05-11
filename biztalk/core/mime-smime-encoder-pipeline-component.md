---
title: MIME-SMIME エンコーダー パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, MIME/SMIME Encoder
- MIME/SMIME Encoder [pipeline component]
- BTS.EncryptionCert property
ms.assetid: 397505e6-47d0-4b63-9197-814ee4388369
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c20197519f6bde52470712175cb632a7309c3609
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65527536"
---
# <a name="mime-smime-encoder-pipeline-component"></a>MIME-SMIME エンコーダー パイプライン コンポーネント
MIME/SMIME エンコーダー コンポーネントは、送信パイプラインのエンコード ステージに配置できます。 7 bit、8 bit、binary、quoted-printable、base64、および UUencode エンコーディングをサポートします。 ローカライズされたデータの文字セットの変更は、エンコーディングには影響ありません。  
  
 このコンポーネントは、いずれかの MIME に使用することができます、エンコードの署名または暗号化と署名証明書による送信メッセージを暗号化します。  
  
 エンコード コンポーネントが構成されている送信パイプラインである場合は、メッセージ、およびパイプラインを実行しているホストを含む BizTalk グループの署名に使用されていない署名証明書を (と適切な送信メッセージは中断されます。エラー)、パイプラインを実行しているホストの保留キューにします。 サービスが実行されている現在のユーザーの個人証明書ストアに署名証明書が見つからない場合は、パイプラインを実行しているホストの保留キューにメッセージが中断されます。  
  
 送信メッセージを暗号化するように構成する送信パイプラインのエンコード コンポーネントがあるし、証明書ストアに証明書が見つかりません場合、は、パイプラインを実行しているホストの保留キューにメッセージが中断されます。  
  
 署名および暗号化されたメッセージを受信する要求-応答ポートで応答を暗号化を実行するには、MIME/SMIME エンコーダー パイプライン コンポーネントの前にパイプラインにカスタム パイプライン コンポーネントを追加する必要があります。 このカスタム パイプライン コンポーネントの暗号化証明書に対応する拇印を識別しに設定する必要があります、 **BTS します。EncryptionCert**メッセージ コンテキストのプロパティ。 メッセージ コンテキスト プロパティの詳細については、次を参照してください。[グループ プロパティを変更する方法](../core/how-to-modify-group-properties.md)します。  
  
 MIME/SMIME エンコーダー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [MIME-SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)します。 暗号化、署名、および証明書の使用状況の BizTalk Server のサポートの詳細については、次を参照してください。[送信と受信メッセージのセキュリティ](../core/security-for-sending-and-receiving-messages.md)します。  
  
## <a name="see-also"></a>参照  
 [パイプライン コンポーネント](../core/pipeline-components.md)   
 [MIME-SMIME プロパティ スキーマおよびプロパティ](../core/mime-smime-property-schema-and-properties.md)   
 [MIME (BizTalk Server サンプル)](../core/mime-biztalk-server-sample.md)