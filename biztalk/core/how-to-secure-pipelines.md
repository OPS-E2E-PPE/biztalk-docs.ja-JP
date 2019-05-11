---
title: パイプラインをセキュリティで保護する方法 |Microsoft Docs
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
ms.openlocfilehash: 9e27ba4d24dd8109366af95b0a477fc8fb049ce5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334824"
---
# <a name="how-to-secure-pipelines"></a>パイプラインをセキュリティで保護する方法

## <a name="authentication-trusted"></a>信頼された認証
ホストとして、管理コンソールでマークできる**信頼されている認証**します。 信頼されている認証としてホストを示す Microsoft BizTalk Server がメッセージのメッセージ コンテキストでそのホストから送信されたセキュリティ関連のプロパティを信頼することを意味します。 セキュリティ関連のプロパティをメッセージ コンテキストでは、 **OriginatorPID**、BTS メッセージ コンテキスト プロパティに対応します。SourcePartyID、および**OriginatorSID**、メッセージ コンテキスト プロパティに対応する**BTS します。WindowsUser**します。 詳細については、次を参照してください。**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  
  
 としてマークされているホスト**認証が信頼された**を信頼されたホストが追加されるメッセージ キュー自体以外のユーザーから、メッセージの送信者として示すためには許可されています。 つまり、としてマークされていないホスト**信頼されている認証**自体以外のメッセージの送信者からキューにメッセージを追加することはできません。  
  
> [!IMPORTANT]
>  MIME/SMIME デコーダー パイプライン コンポーネントでは、暗号化解除証明書の有効期限はチェックしません。 ただし、署名証明書の有効期限はチェックします。  
  
 エンコードおよびデコードの SMTP または HTTP 経由で送信されるメッセージについては、次を参照してください。 [MIME-SMIME エンコーダー パイプライン コンポーネント](../core/mime-smime-encoder-pipeline-component.md)します。 参照してください[MIME/SMIME デコーダー パイプライン コンポーネント](../core/mime-smime-decoder-pipeline-component.md)します。  
  
 ときに、サード パーティの署名の確認については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)します。 参照してください[アグリーメントを作成する方法](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c)します。  
  
## <a name="see-also"></a>参照  
 [パイプライン デザイナーを使用してパイプラインを作成します。](../core/creating-pipelines-using-pipeline-designer.md)   
 [カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)