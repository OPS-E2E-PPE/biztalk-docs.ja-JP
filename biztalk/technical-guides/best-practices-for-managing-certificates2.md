---
title: "Certificates2 を管理するためのベスト プラクティス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71fa00cc-2e0c-46b3-ae62-f130a5b5f4f5
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39f47159fbeacb1b4975cf9f1aa0a8c9a030ecc3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-managing-certificates"></a>証明書を管理するためのベスト プラクティス
このセクションでは、Microsoft の証明書を管理するためのベスト プラクティスを説明[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]環境。  
  
## <a name="assess-and-plan-your-use-of-certificates"></a>評価し、証明書の使用を計画  
 **環境内の脅威モデル分析を行う**  
  
-   使用している環境の脅威モデル分析 (TMA) を実行して、署名証明書または暗号化証明書でセキュリティの脅威を緩和できるかどうかを判断します。  
  
 **パートナーと共に公開キー証明書の計画を作成します。**  
  
-   公開キー証明書を送信して、パートナーから公開キー証明書を受信する計画を作成します。 パーティの解決に署名証明書を使用しない場合は、パブリック証明書をメッセージに添付できます。この場合、使用するシステムで事前に証明書のコピーを用意する必要はありません。  
  
 **公開キーの送信のパートナーとガイドラインを確立します。**  
  
-   パートナーとのサービス レベル契約 (SLA) の一部として、公開キーの送信、証明書の有効期間の終了が近づいた際の通知の受信、証明書が無効になる場合の通知の受け取りに関して、ガイドラインを設定します。  
  
## <a name="install-certificates"></a>証明書をインストールします。  
 **設定された間隔で証明書失効リストをダウンロードします。**  
  
-   設定した間隔で、証明機関 (CA) から証明書の失効一覧 (CRL) をダウンロードします。 週に 1 度の実行をお勧めします。 BizTalk サーバーが参加しているドメインの CA がある場合、CRL は自動的にダウンロードされます。  
  
 **署名証明書を確認してください。**  
  
-   署名証明書を証明書の失効一覧と照合して確認します。 署名証明書を確認する方法の詳細については、次を参照してください。 [MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法](http://go.microsoft.com/fwlink/?LinkId=155145)(http://go.microsoft.com/fwlink/?LinkId=155145) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
 **パートナーと証明書を管理します。**  
  
-   パートナー管理に含まれる作業として、証明書の管理を行います。 BizTalk Server 環境でパーティの追加または削除を行う場合は、そのパートナーに関連付けられた証明書の追加または削除を行うことをお勧めします。  
  
 **ホスト インスタンスを削除する前に証明書を削除します。**  
  
-   BizTalk サーバーからホスト インスタンスを削除する前に、ホスト インスタンスの実行に使用されているアカウントの個人用ストアにある証明書を削除します。  
  
## <a name="configure-biztalk-server-to-use-certificates-for-mimesmime"></a>MIME/SMIME の証明書を使用する BizTalk Server を構成します。  
 **サービス拒否攻撃のデジタル署名用の回避します。**  
  
-   BizTalk Server は、デジタル署名を検証できない場合に、メッセージで実行する対象を決定します。 受信ポートで認証プロパティを設定すると、サービス拒否攻撃を防ぐに役立ちます。  
  
    > [!NOTE]  
    >  認証 - メッセージの削除と認証 - 受信ポートのフラグは、パーティの解決パイプライン コンポーネントが正しく構成することと、BizTalk Server でパーティが定義されている必要があります。 メッセージの保持します。 詳細については、次を参照してください。[パーティの解決パイプライン コンポーネント](http://go.microsoft.com/fwlink/?LinkId=155146)(http://go.microsoft.com/fwlink/?LinkId=155146) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
 **独立した作成用暗号化および暗号化されていないメッセージの受信場所**  
  
-   パートナーから MIME 暗号化されているメッセージと暗号化されていないメッセージを受信することが予測される場合は、それぞれに対して異なるホストの異なる受信場所を作成します。 MIME 暗号化されたメッセージのみを行うには非 MIME メッセージを許可するオプションは [いいえ] に、MIME/SMIME デコーダ パイプライン コンポーネントで構成します。  
  
## <a name="configure-a-biztalk-adapter-to-use-certificates"></a>証明書を使用する BizTalk アダプターを構成します。  
 **ターゲットの Web サイトへの接続をテストします。**  
  
-   SSL を使用している場合は、HTTP または SOAP トランスポートを持つターゲットの Web サイトに接続する前に、Microsoft Internet Explorer® でターゲットの Web サイトに接続できることを確認します。 ダイアログ ボックスが表示されないこと Internet Explorer でターゲットの Web サイトに接続する場合を確認します。 BizTalk Server には、ターゲットの web サイトに接続するときに表示されるダイアログ ボックスをやりとりするためのメカニズムはありません。 ターゲットの Web サイト名が SSL 証明書、Web サイトに指定された名前と一致しない場合、または SSL 証明書のルート証明機関が適切な信頼されたルート証明書でない場合、Internet Explorer で、ダイアログ ボックスを表示可能性があります。機関のストア。  
  
 **SSL 診断ツールを使用して、SSL 接続の問題を分析するには**  
  
-   SSL 診断ツールは、IIS 診断ツールキットのオプションのコンポーネントです。 IIS 診断ツールキットをダウンロードすることができます、[インターネット情報サービスの診断ツール](http://go.microsoft.com/fwlink/?LinkID=64426)ページ (http://go.microsoft.com/fwlink/?LinkID=64426)。  
  
## <a name="exporting-a-certificate-from-one-biztalk-group-to-another"></a>1 つの BizTalk グループから別の証明書のエクスポート  
 **本来の目的、インポートされた証明書を使用していることを確認してください。**  
  
-   グループに証明書をインポートした場合、インポートした証明書は、意図された用途と整合性がある使用法プロパティが必要です。 使用法プロパティを確認するで証明書をダブルクリック、**証明書管理コンソール**インターフェイスをクリックして、**詳細**のタブ、**証明書**ダイアログ ボックス。 をクリックして、**すべて**オプションを**表示**ドロップダウン リストをクリックし、選択、**キー使用法**や**拡張キー使用法**フィールド使用目的を確認します。 BizTalk Server が、その使用目的以外の証明書を使用しようとしています。 ランタイム エラーが発生します。