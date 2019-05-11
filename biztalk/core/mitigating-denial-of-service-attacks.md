---
title: 攻撃のサービス拒否攻撃を緩和 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9595bf828a1960f50090371232f25282fed21b6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394421"
---
# <a name="mitigating-denial-of-service-attacks"></a>攻撃のサービス拒否攻撃の緩和
BizTalk server とサービスの拒否攻撃からサービスを保護するために、次の軽減策の手法を使用することをお勧めします。 これらの緩和方法のうちは環境に適したを決める必要があります。  
  
-   **受信ポートの Authentication Required プロパティを使用します。** 不明なまたは未解決のパーティ (Guest) から来た場合でも既定では、BizTalk がメッセージ ボックス データベースに受信したすべてのメッセージを送信します。BizTalk Server に多数のメッセージを送信し、飽和状態になる (いっぱいになる) 攻撃者の可能性を軽減するために、メッセージ ボックス データベースを使用できます、**に必要な認証**のみ受信する受信ポートのプロパティBizTalk Server はパーティから送信されるメッセージ。 不明なパーティから送られたメッセージを削除するか、それらを中断することができます。 詳細については、**に必要な認証**プロパティを参照してください[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)します。 加え、**に必要な認証**プロパティ、ファイアウォール ポートのフィルタ リングまたは IP アドレスがサービス拒否攻撃から保護するためにブロックなどの外部メカニズムの使用を検討する必要があります。  
  
-   **BizTalk が受信できるメッセージのサイズを制限します。** たとえば、使用すると、SOAP 受信アダプター maxRequestLength 属性を設定して非常に大きいサイズのメッセージの受信を回避できます、 \<httpRuntime\>可能なサイズに要素。 \<HttpRuntime\>にある Machine.config ファイルで要素が定義されている、 \<*ドライブ*\>:\\<*Windowsディレクトリ*\>\Microsoft.NET\Framework\vX.X.XXXXX\CONFIG ディレクトリ。 詳細については\<httpRuntime\>要素では、Microsoft MSDN Web サイトを参照して[ http://go.microsoft.com/fwlink/?LinkId=60948](http://go.microsoft.com/fwlink/?LinkId=60948)します。  
  
-   **強力な Dacl を使用して受信場所です。** 受信場所の格納場所で、強力な随意アクセス制御リスト (Dacl) を使用することをお勧めします。 たとえば、許可されたユーザーだけがこの場所でメッセージをドロップできるように元のファイルの受信場所がメッセージを取得するディレクトリに強力な Dacl を使用する必要があります。  
  
-   **IPSec を使用します。** 表示されない場合、ハードウェアまたはソフトウェア ファイアウォールを使用して、別の BizTalk Server が 1 つのサーバーから転送には、メッセージとデータを保護するためにインターネット プロトコル セキュリティ (IPSec) を使用しています。 IPSec の詳細については、Microsoft ダウンロード センターを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=60949](http://go.microsoft.com/fwlink/?LinkId=60949)します。  
  
## <a name="see-also"></a>参照  
 [潜在的な脅威を識別します。](../core/identifying-potential-threats.md)   
 [セキュリティの計画](../core/planning-for-security.md)