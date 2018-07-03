---
title: Certificates1 を管理するためのベスト プラクティス |Microsoft Docs
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
ms.openlocfilehash: b9aaf8c42b2b0d96e44323af6ee4a0e164a3f46c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004203"
---
# <a name="best-practices-for-managing-certificates"></a>証明書を管理するためのベスト プラクティス
ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で証明書を管理する際のベスト プラクティスについて説明します。  
  
- **環境内の脅威モデル分析を行う**  
  
   使用している環境の脅威モデル分析 (TMA) を実行して、署名証明書または暗号化証明書でセキュリティの脅威を緩和できるかどうかを判断します。  
  
- **パートナーと共に公開キー証明書の計画を作成します。**  
  
   パートナーと共に公開キーの証明書の送受信の計画を作成します。 パーティの解決に署名証明書を使用しない場合は、パブリック証明書をメッセージに添付できます。この場合、使用するシステムで事前に証明書のコピーを用意する必要はありません。  
  
- **設定された間隔で、証明書失効リストをダウンロードします。**  
  
   設定した間隔で、証明機関 (CA) から証明書の失効一覧 (CRL) をダウンロードします。 週に 1 度の実行をお勧めします。 BizTalk サーバーが参加しているドメインの CA がある場合、CRL は自動的にダウンロードされます。  
  
- **パートナーと公開キーを送信するためのガイドラインを確立します。**  
  
   パートナーとのサービス レベル契約 (SLA) の一部として、公開キーの送信、証明書の有効期間の終了が近づいた際の通知の受信、証明書が無効になる場合の通知の受け取りに関して、ガイドラインを設定します。  
  
- **署名証明書を確認します。**  
  
   署名証明書を証明書の失効一覧と照合して確認します。 署名証明書を確認する方法の詳細については、次を参照してください。 [MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)します。  
  
- **デジタル署名に対するサービス拒否攻撃の拒否を防ぐ**  
  
   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がデジタル署名を検証できなかった場合に、そのメッセージをどのように取り扱うかについて決定します。 設定、**認証**受信ポートのプロパティにサービス拒否攻撃が防止されます。  
  
  > [!NOTE]
  >  **認証 - メッセージの削除**と**認証 - メッセージの保持**受信ポートのフラグは、パーティの解決パイプライン コンポーネントを正しく構成することが必要ですし、パーティであります。BizTalk Server で定義されます。 パーティの解決パイプライン コンポーネントの構成の詳細については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)します。  
  
- **別の作成用暗号化および暗号化されていないメッセージの受信場所**  
  
   パートナーから MIME 暗号化されているメッセージと暗号化されていないメッセージを受信することが予測される場合は、それぞれに対して異なるホストの異なる受信場所を作成します。 MIME 暗号化されたメッセージのみが予想される場合は、構成、**非 MIME メッセージを許可する**オプションにデコード MIME/SMIME パイプライン コンポーネントで**いいえ**します。  
  
- **パートナーと証明書を管理します。**  
  
   パートナー管理に含まれる作業として、証明書の管理を行います。 BizTalk Server 環境でパーティの追加または削除を行う場合は、そのパートナーに関連付けられた証明書の追加または削除を行うことをお勧めします。  
  
- **ホスト インスタンスを削除する前に証明書を削除します。**  
  
   BizTalk サーバーからホスト インスタンスを削除する前に、ホスト インスタンスの実行に使用されているアカウントの個人用ストアにある証明書を削除します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md)   
 [Windows グループおよびユーザー アカウントの管理のベスト プラクティス](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)