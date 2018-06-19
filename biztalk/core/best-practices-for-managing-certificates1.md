---
title: Certificates1 を管理するためのベスト プラクティス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, certificates
- certificates, security
- security, certificates
- certificates, best practices
- best practices, security
- security, best practices
ms.assetid: cd182df4-0fcd-409c-9221-89f92e069f07
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e72d87530e5d080bd98ed55c2d29ca9554430375
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232090"
---
# <a name="best-practices-for-managing-certificates"></a>証明書を管理するためのベスト プラクティス
ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で証明書を管理する際のベスト プラクティスについて説明します。  
  
-   **環境内の脅威モデル分析を行う**  
  
     使用している環境の脅威モデル分析 (TMA) を実行して、署名証明書または暗号化証明書でセキュリティの脅威を緩和できるかどうかを判断します。  
  
-   **パートナーと共に公開キー証明書の計画を作成します。**  
  
     パートナーと共に公開キーの証明書の送受信の計画を作成します。 パーティの解決に署名証明書を使用しない場合は、パブリック証明書をメッセージに添付できます。この場合、使用するシステムで事前に証明書のコピーを用意する必要はありません。  
  
-   **設定された間隔で証明書失効リストをダウンロードします。**  
  
     設定した間隔で、証明機関 (CA) から証明書の失効一覧 (CRL) をダウンロードします。 週に 1 度の実行をお勧めします。 BizTalk サーバーが参加しているドメインの CA がある場合、CRL は自動的にダウンロードされます。  
  
-   **公開キーの送信のパートナーとガイドラインを確立します。**  
  
     パートナーとのサービス レベル契約 (SLA) の一部として、公開キーの送信、証明書の有効期間の終了が近づいた際の通知の受信、証明書が無効になる場合の通知の受け取りに関して、ガイドラインを設定します。  
  
-   **署名証明書を確認してください。**  
  
     署名証明書を証明書の失効一覧と照合して確認します。 署名証明書を確認する方法の詳細については、次を参照してください。 [- MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)です。  
  
-   **サービス拒否攻撃のデジタル署名用の回避します。**  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がデジタル署名を検証できなかった場合に、そのメッセージをどのように取り扱うかについて決定します。 設定、**認証**受信ポートのプロパティにサービス拒否攻撃が防止されます。  
  
    > [!NOTE]
    >  **認証]-[メッセージの削除**と**認証]-[メッセージの保持**受信ポートのフラグがパーティの解決パイプライン コンポーネントが正しく構成することを必要とし、パーティであります。BizTalk Server で定義されます。 パーティの解決パイプライン コンポーネントの構成の詳細については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)です。  
  
-   **独立した作成用暗号化および暗号化されていないメッセージの受信場所**  
  
     パートナーから MIME 暗号化されているメッセージと暗号化されていないメッセージを受信することが予測される場合は、それぞれに対して異なるホストの異なる受信場所を作成します。 MIME 暗号化されたメッセージのみを行うには、構成、**非 MIME メッセージを許可する**オプションで、MIME/SMIME デコーダ パイプライン コンポーネントを**いいえ**です。  
  
-   **パートナーと証明書を管理します。**  
  
     パートナー管理に含まれる作業として、証明書の管理を行います。 BizTalk Server 環境でパーティの追加または削除を行う場合は、そのパートナーに関連付けられた証明書の追加または削除を行うことをお勧めします。  
  
-   **ホスト インスタンスを削除する前に証明書を削除します。**  
  
     BizTalk サーバーからホスト インスタンスを削除する前に、ホスト インスタンスの実行に使用されているアカウントの個人用ストアにある証明書を削除します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md)   
 [Windows グループとユーザー アカウントを管理するためのベスト プラクティス](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)