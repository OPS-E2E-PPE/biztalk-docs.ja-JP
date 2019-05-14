---
title: 既知の Issues5 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, known issues
- BizTalk Accelerator for SWIFT, known issues
- known issues
ms.assetid: 0f1ec7dd-9e74-479a-bdc8-ab9c4397c992
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f20477988a3a4f60522a7c05270e72ac525dead
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377307"
---
# <a name="known-issues"></a>既知の問題
このセクションには、Microsoft によるエラーの回避に役立つ有用な情報が含まれています。[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]します。 既知の問題は次の分野に分かれています。  
  
## <a name="message-repair-and-new-submission"></a>Message Repair and New Submission

#### <a name="printing-of-a-repair-document-is-recorded-in-the-history-log-even-if-canceled"></a>取り消された場合でも、修復ドキュメントの印刷が履歴ログに記録されます。  
 修復受信トレイでドキュメントの印刷コマンドを実行して、印刷をキャンセルして、印刷は履歴ログにも入力されます。 これはで修復するドキュメントを開くときに発生します。 その[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、ファイル メニューの [印刷] をクリックし、[印刷] ダイアログ ボックスで [キャンセル] をクリックします。 履歴ログのエントリを無視する必要があります。  
  
#### <a name="a-duplicate-signature-can-cause-an-xlangs-error-message"></a>重複する署名は、xlang/s エラー メッセージを表示できます。  
 検証機能の修理会社として、同じ証明書を使用するときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージを中断し、重複する署名は許可されていないエラー メッセージのことを示します。 ただし、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]も xlang/s サービスが中断されたことを示す、xlang/s のイベント ソースを別のエラー メッセージが生成されます。 このメッセージは無視してかまいません。  
  
#### <a name="message-size-can-affect-repair-performance"></a>メッセージのサイズは、修復のパフォーマンスに影響を与える  
 XML ファイルを開く場合は、一般に大きい XML ファイルを修復しようとすると、システムのパフォーマンスが大幅に低下、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]メッセージの種類のフォームです。 メモリ消費量を増やすことができます、CPU 消費率が低下して、プロセスが十分な記憶域が、操作を完了したことを示すエラーで失敗します。  
  
#### <a name="the-last-signature-used-to-sign-a-message-successfully-will-be-authenticated-by-authenticate-signatures"></a>署名の認証によってメッセージを正常に署名に使用する最後の署名を認証します。  
 認証の署名 ボタンをクリックして、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームにのみかどうか、フォームが署名済みステージの署名を検証します。 前のステージでは、署名を検証、それ以外の場合、1 つを使用する必要がある場合と、次のエラーを投稿します。  
  
 部門 < department_name > で < stage_name > ロールの署名が正しく構成されていません。  
  
 たとえば、検証ステージの直後に、承認ステージであることをとします。 まだサインインしていない、承認者として、フォーム認証の署名をクリックすると[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]検証ツールを使用する署名、承認者の署名ではないを認証し、前のエラーを投稿します。  

#### <a name="a4swift-cleanup-tool-doesnt-delete-templates"></a>A4SWIFT クリーンアップ ツールは、テンプレートを削除しません。  
 A4SWIFT クリーンアップ ツールには、次の操作を実行しません。  
  
-   MRSR サイトから MT のすべてのテンプレートを削除します。  
  
-   MRSR サイトからすべての契約とパートナー プロファイルを削除します。  
  
-   すべてのユーザー、ロール、および部門を削除します。  
  
-   A4SWIFT の BizTalk Server MRSR サイトからの登録を解除します。  
  
#### <a name="the-a4swiftmrsrdepartment-property-is-set-to-an-empty-string-for-a-message-that-did-not-parse"></a>A4SWIFT_MRSRDepartment プロパティが空の文字列を解析できませんでしたメッセージに設定します。  
 メッセージ修復オーケストレーションは、修正された未解析メッセージをメッセージ ボックスにルーティング、ときに設定されます、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_MRSRDepartment プロパティに空の文字列と、昇格させることです。 送信ポートはこのプロパティでサブスクライブできません。  
  
#### <a name="cannot-save-a-department-if-the-sso-service-has-been-stopped"></a>SSO サービスが停止された場合、部署を保存できません。  
 プライマリ SSO サーバーことを示すエラーを受信するが、SSO サービスが停止したときに、部門を追加しようとすると場合、 \<machinename\>できませんでした。 SSO が構成されていることと、そのサーバーで SSO サービスが実行されていることを確認します。  
  
#### <a name="a-department-name-must-not-contain-the-character-"></a>部門名には文字が含まれていない必要があります"~"  
 文字を含む部署名"~"A4SWIFT データベースに問題が発生します。  
  
#### <a name="signing-infopath-forms"></a>Infopath フォームの署名  
 InfoPath フォームの署名は、手動で行う必要があります。  
  
## <a name="security"></a>セキュリティ

#### <a name="mixing-trusted-and-untrusted-hosts-can-enable-spoofing"></a>信頼と信頼されていないホストの混在できるようにスプーフィング  

 その他の信頼されていないから SWIFT 宛てのメッセージを偽装する可能性があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションをホストします。 これは、混在信頼モードで実行されている場合の問題のみ (信頼されたホストと信頼されていないホスト アプリケーションを実行と同じ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]グループ)。 SWIFT バインドのメッセージのソースを識別するためにパーティの解決パイプライン コンポーネントを使用して、このリスクを軽減できます。 これは完全に信頼された環境や使用シナリオの大半を実行している場合に必要ありません。 従う必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]混在している場合は、セキュリティで保護されたアプリケーションを構築するためのガイドラインが信頼されているし、ホストが信頼されていません。 
 
## <a name="miscellaneous"></a>その他

#### <a name="the-cacheentries-setting-may-be-reset-by-a-setup-program-affecting-performance"></a>CacheEntries 設定をリセットするセットアップ プログラムでは、パフォーマンスに影響を与える  
 CacheEntries のレジストリ キーは、ビジネス ルール エンジン更新サービスによってキャッシュされるルール セットの最大数を決定します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セットアップ プログラムは、既定で 32 CacheEntries を設定します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ プログラムは、hkey_local_machine \software を変更\\Microsoft \BusinessRules\3.0\CacheEntries 最適なパフォーマンスの 512 にします。 ただし、特定の状況で CacheEntries が自動的にリセットされます。 システムのパフォーマンスに影響を与える可能性があります。  
  
 ルール エンジンの更新は、512 の CacheEntries を 32 に変更できます。 ルール エンジン更新プログラムをインストールすると、手動でリセット CacheEntries 512 に必要な場合。  
  
 場合でも、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ プログラムでは、32 から CacheEntries を設定を 512、アンインストール[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]32 512 CacheEntries はリセットされません。  
  
 詳細については、BizTalk Server ヘルプの「ルール エンジンの構成およびチューニング パラメーター」トピックを参照してください。  
  
#### <a name="building-a-pipeline-project-may-result-in-a-large-number-of-warnings"></a>パイプライン プロジェクトのビルドの警告の数が多い可能性があります。  
 送信パイプラインまたは受信パイプラインに SWIFT 逆アセンブラーに SWIFT アセンブラーを追加し、これらのパイプラインを含むパイプライン プロジェクトをビルドすると、一連のパイプライン コンポーネントに関連する警告があります。 これらの警告は、Visual Studio が依存関係を見つけられなかったことを示します。 次のように、参照 フォルダーで SWIFTAsm または SWIFTDasm アセンブリのローカル コピー プロパティを変更することでこれらの警告につながる条件を修正できます。  
  
1.  ソリューション エクスプ ローラーの Visual Studio で、パイプライン プロジェクトを展開してから、**参照**ノード。  
  
2.  [参照] ノードを選択、 **SWIFTAsm**アセンブリや、 **SWIFTDasm**アセンブリ。  
  
3.  プロパティ ペインでの値を変更、**ローカル コピー**プロパティを**False**します。  
  
4.  パイプライン プロジェクトを右クリックし、クリックして**ビルド**します。  
  
    > [!NOTE]
    >  見つからない依存関係に関する警告が表示されません。   