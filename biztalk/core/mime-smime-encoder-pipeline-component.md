---
title: MIME/SMIME エンコーダー パイプライン コンポーネント |Microsoft ドキュメント
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
ms.openlocfilehash: d6c6a79052d3294420c46bff2a1ce3c0ed869e48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263066"
---
# <a name="mime-smime-encoder-pipeline-component"></a>MIME/SMIME エンコーダー パイプライン コンポーネント
MIME/SMIME エンコーダー コンポーネントは、送信パイプラインのエンコード ステージに配置できます。 サポートされているエンコードは、7bit、8bit、binary、quoted-printable、base64、および UUencode です。 データのローカライズによって文字セットが変わっても、エンコードは変更されません。  
  
 このコンポーネントは、MIME エンコードのほか、暗号化証明書や署名証明書による送信メッセージの署名および暗号化に使用できます。  
  
 メッセージに署名を施すように構成されたエンコード コンポーネントが送信パイプラインに存在していても、そのパイプラインの実行ホストの BizTalk グループが署名証明書を使って構成されていなかった場合、送信メッセージは中断され (該当するエラーが発生する)、パイプラインを実行しているホストの保留キューに移動されます。 サービスの実行に使用されているアカウント (現在のユーザー) の個人証明書ストアに署名証明書が見つからなかった場合、メッセージは中断され、パイプラインを実行しているホストの保留キューに移動されます。  
  
 送信メッセージを暗号化するように構成されたエンコード コンポーネントが送信パイプラインに存在していても、その証明書が証明書ストアに見つからない場合、メッセージは中断され、パイプラインを実行しているホストの保留キューに移動されます。  
  
 署名または暗号化されたメッセージを受け取る要求 - 応答ポートで応答を暗号化する場合は、MIME/SMIME Encoder パイプライン コンポーネントの前のパイプラインにカスタム パイプライン コンポーネントを追加する必要があります。 このカスタム パイプライン コンポーネントは、暗号化証明書に対応する拇印を識別する必要がありますに設定し、 **BTS です。EncryptionCert**メッセージ コンテキストのプロパティです。 メッセージ コンテキスト プロパティの詳細については、次を参照してください。[グループのプロパティを変更する方法](../core/how-to-modify-group-properties.md)です。  
  
 MIME/SMIME エンコーダー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [- MIME/SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)です。 暗号化、署名、および証明書の使用状況の BizTalk Server サポートに関する詳細については、次を参照してください。[送信および受信メッセージのセキュリティを](../core/security-for-sending-and-receiving-messages.md)です。  
  
## <a name="see-also"></a>参照  
 [パイプライン コンポーネント](../core/pipeline-components.md)   
 [MIME/SMIME プロパティ スキーマおよびプロパティ](../core/mime-smime-property-schema-and-properties.md)   
 [MIME (BizTalk Server サンプル)](../core/mime-biztalk-server-sample.md)