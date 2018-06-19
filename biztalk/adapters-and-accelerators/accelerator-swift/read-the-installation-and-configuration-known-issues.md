---
title: インストールと構成の既知の問題を読み取る |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c58d9dcb-7835-4181-a6cb-203c5d138e6a
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83bbeec3430f479d28502e818b9ead402278f9b1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962008"
---
# <a name="read-the-installation-and-configuration-known-issues"></a>インストールと構成の既知の問題を読み取る
  
## <a name="installing-over-terminal-server-creates-log-files-in-a-different-folder"></a>別のフォルダーにログ ファイルを作成するターミナル サーバー経由でインストールします。  
 A4SWIFT セットアップ プログラムによって作成、セットアップと構成ログ ファイルで、ターミナル サーバー接続を介して A4SWIFT をインストールするときに、 *\<ドライブ\>*: \Documents and 設定\\*\<ユーザー名\>* \Local Settings」フォルダーです。 通常、セットアップ プログラムがでこれらのファイルを作成、 *\<ドライブ\>*: \Documents and 設定\\*\<ユーザー名\>* \LocalSettings\temp フォルダーです。 コンピューターを設定し、適切に構成されていることを確認するこれらのログ ファイルを確認することができます。  
  
## <a name="silent-installation-is-not-recommended"></a>サイレント インストールはお勧めしません  
 サイレント インストールでは、A4SWIFT セットアップ プログラムがサポートされますが、必要な追加の構成手順の複雑であるためお勧めできません。  
  
## <a name="a4swift-setup-runs-with-the-installplatform-argument-that-overwrites-dlls-for-visualstudionet"></a>VisualStudio.Net の Dll を上書きする/InstallPlatform 引数を持つ A4SWIFT セットアップが実行されます。  
 A4SWIFT セットアップ プログラムは、常に/InstallPlatform 引数で実行されます。 その結果、A4SWIFT セットアップ常に msvcr71.dll、mfc71u.dll、msvcp71.dll、およびインストール atl71.dll、必要な[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 A4SWIFT セットアップは、Dll 前にインストールされたかどうかどうか、%WINDIR%\System32 フォルダーにこれらの DLL ファイルをインストールします。  
  
## <a name="canceling-a4swift-configuration-will-fail"></a>A4SWIFT の取り消しの構成は失敗します  
 クリックすると**キャンセル**A4SWIFT 中に構成は取り消すことができません構成します。 構成プロセスは、完了するまで続行されます。  
  
## <a name="after-unconfiguring-a4swift-you-cannot-reconfigure-in-the-same-instance-of-the-configuration-console"></a>A4SWIFT を構成解除した後、構成コンソールの同じインスタンスで再構成することはできません。  
 A4SWIFT、または A4SWIFT のコンポーネントの構成を解除する場合は、最初、A4SWIFT 構成コンソールを閉じると、それを開くことがなく A4SWIFT またはそのコンポーネントを再構成することはできません。 これを行わないと、構成コンソールの特定のフィールドがグレー表示し、それらの値を選択することはできません。  
  
## <a name="configuration-of-a-web-components-only-installation-will-succeed-even-if-no-a4swift-database-exists"></a>A4SWIFT データベースが存在しない場合でも Web コンポーネントのみのインストールの構成が正常に終了されます。  
 Message Repair and New Submission の機能の Web コンポーネントのみをインストールするカスタム インストールを実行し、実行した、Microsoft BizTalk Accelerator for SWIFT の構成ウィザード場合、構成プログラムが正常にも完了します。A4SWIFT データベースはありません。  
  
 A4SWIFT データベースが表示されます、 **Message Repair and New Submission の Web コンポーネント**A4SWIFT 構成ダイアログ ボックスのペイン、そのデータベースが存在しない場合でもです。 警告は、A4SWIFT の表示、データ内のデータベースに格納 ウィンドウで、警告いなくてできるように、構成プロセスを続行されます。  
  
## <a name="upgrade-process-does-not-create-a-new-root-folder"></a>アップグレード プロセスは、新しいルート フォルダーを作成できません。  
 アップグレード プロセスが、既存の A4SWIFT ファイルを更新*\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for A4SWIFT 2.3/3.0 フォルダーです。 アップグレードされたファイル用の新しいフォルダーが作成されず、また既存のフォルダーの名前は変更*\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT です。  
  
## <a name="canceling-setup-during-an-upgrade-for-a4swift-may-leave-your-system-in-an-unknown-state"></a>A4SWIFT のアップグレード中にセットアップを取り消すことがありますのままにして、システム状態が不明で  
 クリックすると、一部のシナリオで、**キャンセル**アップグレード中にはファイル、アセンブリ、BizTalk Server アイテム、およびレジストリ キーはそのまま残すセットアップのロールバックが完了した後です。  
  
 すべてのアイテムを手動で削除します。  
  
## <a name="download-the-a4swift-setup-exe-file-from-the-web-into-a-temp-folder"></a>Web から一時フォルダーに A4SWIFT セットアップ exe ファイルをダウンロードします。  
 A4SWIFT を Web からダウンロードした自己解凍実行可能ファイルからインストールしようとする場合は、temp フォルダーにそのファイルをダウンロードすることを確認します。 BizTalk サーバーのルート フォルダーにファイルをダウンロードできません (\Program Files\Microsoft BizTalk Server \<*バージョン*\>)。  
  
 BizTalk サーバーのルート フォルダーから、exe ファイルを実行する場合、A4SWIFT セットアップ ウィザードではなくのセットアップ ウィザードが、BizTalk Server で実行されます。  
  
## <a name="installing-a4swift-in-a-location-other-than-the-default-requires-changes-to-the-bredeploymentexeconfig-file"></a>BREDeployment.exe.config ファイルへの変更、既定以外の場所に A4SWIFT をインストールする必要があります。  
 をインストールする BizTalk Accelerator for SWIFT %programfiles%\Microsoft BizTalk アクセラレータの既定パス以外のパスに SWIFT の場合は、正しいパスを反映するように、製品の \tools サブディレクトリにある BREDeployment.exe.config ファイルを編集する必要がありますBasePoliciesDirectory、SchemasDirectory、および VocabularyDirectory です。  
  
 関連するルールやボキャブラリを正常に展開する、プロジェクトに含まれる SWIFT スキーマに関連付けられているルールのいずれかを展開する前にこの変更を行う必要があります。  
  
## <a name="message-repair-is-not-supported-for-certain-batched-message-scenarios"></a>特定のバッチ メッセージ シナリオのメッセージの修復はサポートされていません  
 A4SWIFT には、断片化がバッチ処理のシナリオに対してのみのメッセージの修復がサポートされています。 これらのシナリオでは、バッチ処理されたメッセージのインターチェンジの部分のみを修復できます。  
  
## <a name="you-cannot-submit-a-fixed-unparsed-message-from-a-mrsr-site-library-named-anything-other-than-unparsed"></a>Unparsed 以外の何かという名前の MRSR サイト ライブラリから固定未解析のメッセージを送信することはできません。  
 A4SWIFT できません"Unparsed"名前が付いていないライブラリからのメッセージを送信して正常にあるため、操作は失敗"Unparsed"名前が付いていない MRSR サイトのドキュメント ライブラリから修正した未解析のメッセージを送信しようとすると、  
  
 Message Repair and 調整機能をインストールする前に、既存の「未解析」ドキュメント ライブラリを MRSR サイトにある、A4SWIFT セットアップは、サフィックスを持つ「未解析」というタイトル未解析のメッセージのライブラリを作成します。  
  
 A4SWIFT を解析できないメッセージを受信すると、セットアップを作成したライブラリにメッセージをルーティングします。 ただし、そのライブラリからのメッセージを送信しようとすると、操作が失敗します。  
  
 この問題は通常、A4SWIFT をアンインストールして MRSR サイトから「未解析」のドキュメント ライブラリを削除しない場合に発生します。  このような状況 SWIFT を再インストールするときに、セットアップを作成新しいドキュメント ライブラリ名前"Unparsed"サフィックスを持つ。"  
  
 この問題を解決するには、この手順に従います。  
  
#### <a name="to-name-a-library-unparsed-in-order-to-submit-unparsed-messages"></a>未解析のメッセージを送信するためにライブラリ"Unparsed"の名前を付ける  
  
1.  メッセージの修復と調整の機能を削除します。  
  
2.  未解析のライブラリを手動で削除します。 これは削除されない A4SWIFT のアンインストール時にします。  
  
3.  Message Repair and 調整を再インストールします。 再インストール中には、"Unparsed"という名前のドキュメント ライブラリが作成され、このドキュメント ライブラリを通じて固定未解析メッセージを送信することができます。  
  
## <a name="bredeployment-utility-cannot-deploy-or-undeploy-policies-if-a4swift-vocabularies-are-not-correctly-configured"></a>BREDeployment ユーティリティは、展開または A4SWIFT ボキャブラリが正しく構成されていない場合は、ポリシーを展開解除できません。  
 BREDeployment.exe ツールを使用して A4SWIFT ビジネス ルール エンジン ポリシーの展開を解除しようとする BREDeployment.exe 構成ファイルが正しいボキャブラリ ファイルの場所を指していない場合は、このツールは、エラーを報告可能性があります。 この問題は、BREDeployment.exe 構成ファイル内の場所を変更すると、新しい場所にボキャブラリ ファイルが含まれていないがあります。 ボキャブラリが見つかりませんでした。 構成ポリシーの展開または展開解除を停止することを知らせるエラーが表示されます。  
  
 この問題を解決するには、標準を使用して**ビジネス ルール エンジン展開ウィザード**です。 UI の詳細については[!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-swift/known-issues5.md)