---
title: "攻撃のサービス拒否攻撃を緩和 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IPSec, message protection
- messages, size
- security, configuring
- Authentication Required property
- security, Internet Information Services (IIS) Lockdown Tool
- security, Denial of Service attacks
- discretionary access control lists (DACLs)
- IPSec, data protection
- Internet Information Services (IIS) Lockdown Tool
- Denial of Service attacks
ms.assetid: f39c0d0a-b890-4c48-874d-5cafbc71473c
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94fe45a2882d85164ab81c13e78fca2ac26d0ec4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mitigating-denial-of-service-attacks"></a>攻撃のサービス拒否攻撃の緩和
サービスの拒否攻撃から BizTalk Server とサービスを保護するには、次の緩和方法を使用することをお勧めします。 どの緩和方法が環境に適しているのかを判断してください。  
  
-   **受信ポートの Authentication Required プロパティを使用します。** 既定では、BizTalk はメッセージ ボックス データベースに受信したすべてのメッセージを送信します。メッセージの送信元が不明なパーティまたは未解決のパーティ (ゲスト) である場合も同様です。BizTalk Server に大量のメッセージを送信して、いっぱいになる (いっぱい) 攻撃者の可能性を軽減するために、メッセージ ボックス データベースを使えば、**認証を必要と**のみ受信する受信ポートのプロパティBizTalk Server はパーティから送信されるメッセージ。 不明なパーティからのメッセージをドロップするか、それらのメッセージを保留するかを選択できます。 詳細については、 **Authentication Required**プロパティを参照してください[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)です。 加え、 **Authentication Required**プロパティ、ファイアウォール ポートのフィルタ リングまたは IP アドレスのサービス拒否攻撃を防ぐためにブロックなどの外部メカニズムの使用を検討する必要があります。  
  
-   **BizTalk が受信できるメッセージのサイズを制限します。** たとえばを使用するときに、SOAP 受信アダプター maxRequestLength 属性を設定して非常に大きいサイズのメッセージの受信を避けることができます、 \<httpRuntime > 可能なサイズに要素。 \<HttpRuntime > 要素にある Machine.config ファイルで定義されている、 \<*ドライブ*>:\\<*Windows directory*> \Microsoft.NET\Framework\vX.X.XXXXX\CONFIG ディレクトリ。 詳細については\<httpRuntime > 要素では、Microsoft MSDN Web サイトを参照して[http://go.microsoft.com/fwlink/?LinkId=60948](http://go.microsoft.com/fwlink/?LinkId=60948)です。  
  
-   **強力な Dacl を使用するには、場所が表示されます。** 受信場所のドロップ場所には強力な随意アクセス制御リスト (DACL) を使用することをお勧めします。 たとえば、認証されたユーザーだけがこの場所にメッセージをドロップできるように、ファイルの受信場所がメッセージを取得するディレクトリに強力な DACL を使用する必要があります。  
  
-   **IPSec を使用します。** ハードウェアとソフトウェアのファイアウォールをどちらも使用しない場合、あるサーバーから別のサーバーにメッセージとデータを移動するときに、インターネット プロトコル セキュリティ (IPSec) を使用してメッセージとデータを保護します。 IPSec の詳細については、Microsoft ダウンロード センターを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=60949](http://go.microsoft.com/fwlink/?LinkId=60949)です。  
  
## <a name="see-also"></a>参照  
 [潜在的な脅威を識別します。](../core/identifying-potential-threats.md)   
 [セキュリティの計画](../core/planning-for-security.md)