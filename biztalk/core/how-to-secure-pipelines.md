---
title: パイプラインをセキュリティで保護する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3a717f-acf8-4f08-a6fb-6d1d48b5b80a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 903e9faec81ce58aac243fb7a22bac6678a81a42
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255186"
---
# <a name="how-to-secure-pipelines"></a>パイプラインをセキュリティ保護する方法

## <a name="authentication-trusted"></a>信頼されている認証
ホストとして、管理コンソールでマークできる**信頼されている認証**です。 ホストが [信頼されている認証] としてマークされている場合、そのホストからのメッセージのコンテキストとして送信されたセキュリティ関連のプロパティが、Microsoft BizTalk Server で信頼されます。 セキュリティ関連のプロパティをメッセージ コンテキストでは、 **OriginatorPID**、BTS メッセージ コンテキスト プロパティに対応します。SourcePartyID、および**OriginatorSID**、メッセージ コンテキスト プロパティに対応する**BTS です。WindowsUser**です。 詳細については、次を参照してください。**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
 としてマークされているホスト**認証信頼**は、信頼されたホストが追加されるメッセージをキューに自分以外からのメッセージの送信者としてを示すために使用します。 としてマークされていないホスト言い換えれば、**信頼されている認証**それ自体以外のメッセージの送信者からキューにメッセージを追加することはできません。  
  
> [!IMPORTANT]
>  MIME/SMIME デコーダー パイプライン コンポーネントは、解読証明書の有効期限をチェックしません。 ただし、署名証明書の有効期限はチェックされます。  
  
 エンコードとデコード SMTP または HTTP 経由で送信されたメッセージについては、次を参照してください。 [- MIME/SMIME エンコーダー パイプライン コンポーネント](../core/mime-smime-encoder-pipeline-component.md)です。 参照してください[- MIME/SMIME デコーダー パイプライン コンポーネント](../core/mime-smime-decoder-pipeline-component.md)です。  
  
 サード パーティを処理する場合、署名の検証方法については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)です。 参照してください[アグリーメントを作成する方法](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c)です。  
  
## <a name="see-also"></a>参照  
 [パイプライン デザイナーを使用してパイプラインを作成します。](../core/creating-pipelines-using-pipeline-designer.md)   
 [カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)