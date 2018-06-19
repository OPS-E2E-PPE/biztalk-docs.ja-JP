---
title: MIME/SMIME デコーダー パイプライン コンポーネント |Microsoft ドキュメント
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
ms.openlocfilehash: d85fe099cb876156410ba86c5f204a154dfbac36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263226"
---
# <a name="mime-smime-decoder-pipeline-component"></a>MIME/SMIME デコーダー パイプライン コンポーネント
MIME/SMIME デコーダー コンポーネントは、メッセージに MIME デコード機能を提供します。 このパイプライン コンポーネントは、受信パイプラインのデコード ステージに配置できます。サポートされているエンコードは、7bit、8bit、binary、quoted-printable、UUencode、および base64 です。 データのローカライズによって文字セットが変わっても、デコードは変更されません。  
  
 MIME/SMIME デコーダー コンポーネントを使用すると、受信メッセージを復号化および署名認証できます。 暗号化証明書は、サービスを実行する現在のユーザーの個人証明書ストアから使用されます。 署名認証の証明書は、ローカル コンピューターのアドレス帳ストアまたはメッセージ自体から使用されます。  
  
 メッセージの復号化に成功すると、MIME/SMIME デコーダー パイプライン コンポーネントは、メッセージの述語としてメッセージを復号化するために使用される暗号化証明書の拇印を関連付けます。 これは、メッセージにサブスクライブしているサービス (オーケストレーションまたは送信ポート) をこのキーを所有するホストに関連付ける必要があることを意味しています。 ホストとキー間の関連付けは、BizTalk 管理コンソールで行い、ホストのプロパティで表します。 BizTalk 管理コンソールで、ホストの構成の詳細については、次を参照してください。[ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)です。  
  
 MIME/SMIME デコーダー パイプライン コンポーネントとは、すぐに使用できる受信パイプライン コンポーネントです。このパイプライン コンポーネントでは、マルチパート MIME/SMIME メッセージなどのマルチパート メッセージが処理されます。 パイプライン コンポーネントは、メッセージを解析し、同等のマルチパート BizTalk メッセージを作成します。 マルチパート BizTalk メッセージには、ボディ部というメッセージ固有の部分が 1 つあります。 XML 逆アセンブラー パイプライン コンポーネントなどの他のすべてのパイプライン コンポーネントは、BizTalk メッセージのボディ部だけを処理します。 また、BizTalk ボディ部に対応する MessageType は、サブスクライバーへのメッセージのルーティングに使用されます。  
  
 マルチパート MIME メッセージに対応する BizTalk BodyPart を識別するため、MIME/SMIME デコーダー パイプライン コンポーネントによって次の条件が評価されます。 条件の評価の順番を次に示します。  
  
1.  Content-Description ヘッダーが "body" (大文字と小文字を区別しない) に設定されている、最初の MIME/SMIME 部分。  
  
2.  Content-Type ヘッダーが "text/xml" (大文字と小文字を区別しない) に設定されている、最初の MIME/SMIME 部分。  
  
3.  Content-Type ヘッダーが "text/" (大文字と小文字を区別しない) に設定されている、最初の MIME/SMIME 部分。  
  
4.  最初の MIME/SMIME 部分。  
  
> [!NOTE]
>  BizTalk 出力メッセージにおける上記の各部分の順序は、MIME/SMIME メッセージの MIME/SMIME 部分の順序と同じです。  
  
> [!NOTE]
>  マルチパート BizTalk メッセージがオーケストレーションによってサブスクライブまたは使用されている場合、メッセージの構成部分の数と、オーケストレーションをアクティブにするメッセージの構成部分の数は一致する必要があります。  
  
 MIME/SMIME デコーダー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [- MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)です。 復号化、署名の検証、および証明書の使用状況の BizTalk Server サポートに関する詳細については、次を参照してください。[送信および受信メッセージのセキュリティを](../core/security-for-sending-and-receiving-messages.md)です。  
  
## <a name="see-also"></a>参照  
 [パイプライン コンポーネント](../core/pipeline-components.md)   
 [MIME/SMIME プロパティ スキーマおよびプロパティ](../core/mime-smime-property-schema-and-properties.md)   
 [MIME (BizTalk Server サンプル)](../core/mime-biztalk-server-sample.md)