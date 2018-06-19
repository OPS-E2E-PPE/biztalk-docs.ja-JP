---
title: 既知の Issues5 |Microsoft ドキュメント
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
ms.openlocfilehash: c1356209f700fc7ceff220f4b0f8fcd3dd67db07
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006715"
---
# <a name="known-issues"></a>既知の問題
このセクションでのエラーを回避するために役立つ有用な情報が含まれています。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]です。 既知の問題は次の分野に分かれています。  
  
## <a name="message-repair-and-new-submission"></a>Message Repair and New Submission

#### <a name="printing-of-a-repair-document-is-recorded-in-the-history-log-even-if-canceled"></a>修復ドキュメントの印刷は取り消された場合でも、履歴ログに記録されます。  
 修復受信トレイで、ドキュメントの印刷 コマンドを実行して、印刷をキャンセルして場合、印刷は、履歴ログにも入力されます。 これで修復するドキュメントを開く場合に発生、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、[ファイル] メニューで、[印刷] コマンドをクリックし、[印刷] ダイアログ ボックスで [キャンセル] をクリックします。 履歴ログのエントリを無視してください。  
  
#### <a name="a-duplicate-signature-can-cause-an-xlangs-error-message"></a>重複する署名のエラー メッセージが発生することができます。  
 としてする場合、検証機能は、同じ証明書、修理会社[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージを中断し、重複する署名は許可されていないエラー メッセージのことを示します。 ただし、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]も xlang/s サービスが中断されたことを示す、xlang/s のイベント ソースを別のエラー メッセージが生成されます。 このメッセージは無視してかまいません。  
  
#### <a name="message-size-can-affect-repair-performance"></a>メッセージのサイズは修復のパフォーマンスに影響する可能性  
 XML ファイルを開くと、非常に大きな XML ファイルを修復しようとすると、システムのパフォーマンスが大幅に低下、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]メッセージの種類のフォームです。 メモリ消費量が増えることがあります、CPU 消費率が低下し、処理が十分な記憶域が、操作を完了することを示すエラーで失敗する可能性があります。  
  
#### <a name="the-last-signature-used-to-sign-a-message-successfully-will-be-authenticated-by-authenticate-signatures"></a>署名の認証によってメッセージを正常にサインインに使用する最後の署名を認証します。  
 署名の認証 ボタンをクリックすると、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームとしているにのみフォームに既に署名したかどうか、ステージの署名を検証します。 前のステージでは、署名を検証、それ以外の場合、1 つを使用する必要がある場合と、次のエラーを投稿します。  
  
 部門 < department_name > で < stage_name > ロールの署名が正しく構成されていません。  
  
 たとえば、検証ステージの直後に承認ステージであること。 認証の署名をクリックすると、承認者としてフォームを署名していない[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]検証ツールが使用する署名、承認者の署名ではないを認証し、前のエラーを送信します。  

#### <a name="a4swift-cleanup-tool-doesnt-delete-templates"></a>A4SWIFT クリーンアップ ツールは、テンプレートを削除しません。  
 A4SWIFT のクリーンアップ ツールは、次の操作を実行します。  
  
-   MRSR サイトから MT のすべてのテンプレートを削除します。  
  
-   MRSR サイトからのすべてのアグリーメントとパートナー プロファイルを削除します。  
  
-   すべてのユーザー、ロール、および部門を削除します  
  
-   A4SWIFT の BizTalk Server MRSR サイトからの登録を解除します。  
  
#### <a name="the-a4swiftmrsrdepartment-property-is-set-to-an-empty-string-for-a-message-that-did-not-parse"></a>A4SWIFT_MRSRDepartment プロパティが空の文字列が解析しなかったメッセージに設定します。  
 メッセージ修復オーケストレーションは、修正された未解析のメッセージをメッセージ ボックスにルーティング、ときに設定されます、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]空 _MRSRDepartment プロパティ文字列を昇格させることです。 送信ポートはこのプロパティにサブスクライブすることができません。  
  
#### <a name="cannot-save-a-department-if-the-sso-service-has-been-stopped"></a>SSO サービスが停止している場合、部署を保存できません。  
 場合は、SSO サービスが停止したときに、部門を追加しようとすると、エラーが表示されます、ことを示すプライマリ SSO サーバー \<machinename\>できませんでした。 SSO が構成されていること、およびそのサーバーで SSO サービスが実行されていることを確認してください。  
  
#### <a name="a-department-name-must-not-contain-the-character-"></a>部門名は文字を含めることはできません"~"  
 文字を含む部門名"~"A4SWIFT データベースと問題が発生します。  
  
#### <a name="signing-infopath-forms"></a>Infopath フォームの署名  
 InfoPath フォームの署名は、手動で行う必要があります。  
  
## <a name="security"></a>セキュリティ

#### <a name="mixing-trusted-and-untrusted-hosts-can-enable-spoofing"></a>信頼できる、信頼されていないホストを混在させることができますスプーフィングを有効に  

 他の信頼関係のないから SWIFT 宛てのメッセージになりすます可能性があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションをホストします。 これは、混在信頼モードで実行されている場合の問題である (信頼されたホストと信頼されていないホスト アプリケーションを実行と、同じ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]グループ)。 SWIFT バインドのメッセージのソースを識別するパーティの解決パイプライン コンポーネントを使用して、このリスクを軽減できます。 完全に信頼された環境や使用シナリオの大半を実行している場合は必要ありません。 従う必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]混在している場合は、セキュリティで保護されたアプリケーションを構築するためのガイドラインが信頼されているし、ホストを信頼されていません。 
 
## <a name="miscellaneous"></a>その他

#### <a name="the-cacheentries-setting-may-be-reset-by-a-setup-program-affecting-performance"></a>CacheEntries 設定をリセットするセットアップ プログラムでは、パフォーマンスに影響します。  
 CacheEntries レジストリ キーでは、ビジネス ルール エンジン更新サービスによってキャッシュされるルール セットの最大数を決定します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セットアップ プログラムは、既定では 32 を CacheEntries を設定します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ プログラムは hkey_local_machine \software、変更\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]\BusinessRules\3.0\CacheEntries を最適なパフォーマンスの 512 です。 ただし、特定の状況で CacheEntries が自動的にリセットされます。 システムのパフォーマンスに影響を与える可能性があります。  
  
 ルール エンジン更新プログラムは、512 の CacheEntries を 32 に変更できます。 ルール エンジン更新プログラムをインストールすると、手動でリセット CacheEntries 512 に必要な場合。  
  
 場合でも、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ プログラムは、512、アンインストールを 32 から CacheEntries を設定[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]32 512 CacheEntries はリセットされません。  
  
 詳細については、BizTalk Server ヘルプの「ルール エンジンの構成およびチューニング パラメーター」を参照してください。  
  
#### <a name="building-a-pipeline-project-may-result-in-a-large-number-of-warnings"></a>警告の数が多いパイプライン プロジェクトのビルドがあります。  
 送信パイプラインまたは受信パイプラインに SWIFT 逆アセンブラーに SWIFT アセンブラーを追加し、これらのパイプラインを含むパイプライン プロジェクトをビルドすると、一連のパイプライン コンポーネントに関連する警告が表示されます。 これらの警告は、Visual Studio が依存関係を見つけられなかったことを示します。 次のように、参照 フォルダーで SWIFTAsm または SWIFTDasm アセンブリのローカル コピー プロパティを変更することによってこれらの警告を引き起こす状況を修正することができます。  
  
1.  ソリューション エクスプ ローラーの Visual Studio で、パイプライン プロジェクトを展開し、展開、**参照**ノード。  
  
2.  [参照] ノードを選択、 **SWIFTAsm**アセンブリや、 **SWIFTDasm**アセンブリ。  
  
3.  値を変更、プロパティ ペインで、**ローカル コピー**プロパティを**False**です。  
  
4.  パイプライン プロジェクトを右クリックし、をクリックして**ビルド**です。  
  
    > [!NOTE]
    >  見つかりません。 依存関係に関する警告が表示されません。   