---
title: インストールと構成に関する既知の問題を読み取る |Microsoft Docs
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
ms.openlocfilehash: 56536829ba789903899bdd661a789e5755e0cf3a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377065"
---
# <a name="read-the-installation-and-configuration-known-issues"></a>インストールと構成に関する既知の問題を読み取る
  
## <a name="installing-over-terminal-server-creates-log-files-in-a-different-folder"></a>別のフォルダーにログ ファイルを作成するターミナル サーバー経由でインストールします。  
 A4SWIFT セットアップ プログラムがのセットアップと構成のログ ファイルを作成するターミナル サーバー接続を介して A4SWIFT をインストールするときに、 *\<ドライブ\>*: \Documents and Settings\\ *\<ユーザー名\>* \Local Settings フォルダー。 通常、セットアップ プログラムがでこれらのファイルを作成、 *\<ドライブ\>*: \Documents and Settings\\*\<ユーザー名\>* \LocalSettings\temp フォルダーです。 これらのログ ファイル、コンピューターを設定して、適切に構成されていることを確認するを確認することができます。  
  
## <a name="silent-installation-is-not-recommended"></a>サイレント インストールはお勧めしません  
 サイレント インストールでは、A4SWIFT セットアップ プログラムによってサポートされてが、ために必要な追加の構成手順の複雑さは推奨されません。  
  
## <a name="a4swift-setup-runs-with-the-installplatform-argument-that-overwrites-dlls-for-visualstudionet"></a>A4SWIFT セットアップの動作が/InstallPlatform 引数 VisualStudio.Net の Dll を上書きします。  
 A4SWIFT セットアップ プログラムは、常に/InstallPlatform 引数を実行します。 その結果、A4SWIFT セットアップ常に msvcr71.dll、mfc71u.dll、msvcp71.dll、およびインストール atl71.dll、必要な[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 A4SWIFT セットアップでは、%WINDIR%\System32 フォルダーにこれらの DLL ファイルがインストールされますか、Dll を以前インストールされているかどうか。  
  
## <a name="canceling-a4swift-configuration-will-fail"></a>A4SWIFT のキャンセルの構成が失敗します  
 クリックすると**キャンセル**A4SWIFT 中に構成はキャンセルされません構成します。 構成プロセスは完了するまで続行されます。  
  
## <a name="after-unconfiguring-a4swift-you-cannot-reconfigure-in-the-same-instance-of-the-configuration-console"></a>A4SWIFT を構成解除した後、構成コンソールの同じインスタンスで再構成することはできません。  
 A4SWIFT、または A4SWIFT のコンポーネントの構成を解除する場合は、最初に、A4SWIFT 構成コンソールを閉じると、それを開くことがなく A4SWIFT またはそのコンポーネントを再構成することはできません。 これを行わない場合は、構成コンソールの特定のフィールドはグレー表示、およびそれらの値を選択することはできません。  
  
## <a name="configuration-of-a-web-components-only-installation-will-succeed-even-if-no-a4swift-database-exists"></a>A4SWIFT データベースが存在しない場合でも、Web コンポーネントのみのインストールの構成は成功します  
 Message Repair and New Submission の機能の Web コンポーネントのみをインストールするカスタム インストールを実行して、SWIFT の構成ウィザードには、Microsoft BizTalk Accelerator を実行して場合、構成プログラムはあっても正常に完了します。A4SWIFT データベースはありません。  
  
 A4SWIFT データベースが表示されます、 **Message Repair and New Submission の Web コンポーネント**そのデータベースが存在しない場合でも、[A4SWIFT 構成] ダイアログ ボックスのウィンドウ。 警告は、データ内のデータベース、A4SWIFT の表示ウィンドウを格納しますが、警告妨げません構成プロセス続行からされます。  
  
## <a name="upgrade-process-does-not-create-a-new-root-folder"></a>アップグレード プロセスは、新しいルート フォルダーを作成できません。  
 アップグレード プロセスは、既存の A4SWIFT ファイルを更新*\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for A4SWIFT 2.3/3.0 フォルダー。 アップグレードされたファイル用の新しいフォルダーは作成されませんもに、既存のフォルダーの名前は変更*\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT します。  
  
## <a name="canceling-setup-during-an-upgrade-for-a4swift-may-leave-your-system-in-an-unknown-state"></a>不明な状態で、システムのアップグレード中に A4SWIFT のセットアップの取り消ししまう可能性があります。  
 クリックすると、一部のシナリオで、**キャンセル**アップグレード中にボタンがファイル、アセンブリ、BizTalk Server アイテム、およびレジストリ キーをそのままセットアップのロールバックが完了した後。  
  
 すべてのアイテムを手動で削除できます。  
  
## <a name="download-the-a4swift-setup-exe-file-from-the-web-into-a-temp-folder"></a>A4SWIFT セットアップの exe ファイルを Web から一時フォルダーにダウンロードします。  
 A4SWIFT を Web からダウンロードした自己解凍実行可能ファイルからインストールする場合は、必ず、一時フォルダーにそのファイルをダウンロードします。 BizTalk サーバーのルート フォルダーにファイルをダウンロードできません (BizTalk Server \Program Files\Microsoft \<*バージョン*\>)。  
  
 BizTalk サーバーのルート フォルダーから実行可能ファイルを実行する場合のセットアップ ウィザード、A4SWIFT セットアップ ウィザードではなくが、BizTalk Server で実行されます。  
  
## <a name="installing-a4swift-in-a-location-other-than-the-default-requires-changes-to-the-bredeploymentexeconfig-file"></a>既定値以外の場所に A4SWIFT をインストールするには、BREDeployment.exe.config ファイルへの変更が必要です。  
 をインストールする BizTalk Accelerator for SWIFT %programfiles%\Microsoft BizTalk アクセラレータの既定パス以外のパスで SWIFT の場合は、によって正しいパスを反映するように、製品の \tools サブディレクトリにある BREDeployment.exe.config ファイルを編集する必要がありますBasePoliciesDirectory、SchemasDirectory、および VocabularyDirectory します。  
  
 関連するルールやボキャブラリを正常に展開するプロジェクトに含まれる SWIFT スキーマに関連付けられているルールのいずれかをデプロイする前に、この変更を行う必要があります。  
  
## <a name="message-repair-is-not-supported-for-certain-batched-message-scenarios"></a>バッチ処理されたメッセージの特定のシナリオでは、メッセージの修復はサポートされていません  
 A4SWIFT では、断片化がバッチ処理のシナリオにのみメッセージの修復をサポートしています。 これらのシナリオでは、バッチ処理されたメッセージのインターチェンジの部分のみを修復できます。  
  
## <a name="you-cannot-submit-a-fixed-unparsed-message-from-a-mrsr-site-library-named-anything-other-than-unparsed"></a>Unparsed 以外のものをという名前の MRSR サイト ライブラリから固定未解析メッセージを送信することはできません。  
 A4SWIFT は"Unparsed"という名前がないライブラリからのメッセージが正常に送信できないため、操作は失敗"Unparsed"名前が付いていません MRSR サイトのドキュメント ライブラリからの修正を未解析メッセージを送信しようとすると、  
  
 Message Repair and Reconciliation 機能をインストールする前に、MRSR サイトで「未解析」既存のドキュメント ライブラリをした場合、A4SWIFT セットアップには、サフィックスを持つ「未解析」entitled 未解析メッセージ用のライブラリが作成されます。  
  
 A4SWIFT 受信すると、メッセージを解析できないが、セットアップを作成したライブラリにメッセージをルーティングします。 ただし、そのライブラリからのメッセージを送信しようとすると、操作が失敗します。  
  
 この問題は、A4SWIFT をアンインストールして MRSR サイトから「未解析」のドキュメント ライブラリを削除しない場合に通常発生します。  SWIFT このような状況を再インストール時に、セットアップを作成、新しいドキュメント ライブラリを名前に"Unparsed"サフィックスをします。"  
  
 この問題を解決するには、この手順に従います。  
  
#### <a name="to-name-a-library-unparsed-in-order-to-submit-unparsed-messages"></a>未解析メッセージを送信するにはライブラリ"Unparsed"に名前を付ける  
  
1.  Message Repair and Reconciliation の機能を削除します。  
  
2.  未解析のライブラリを手動で削除します。 これは削除されない A4SWIFT をアンインストールするときにします。  
  
3.  Message Repair and Reconciliation を再インストールします。 再インストール時に、"Unparsed"という名前のドキュメント ライブラリが作成され、このドキュメント ライブラリを介した固定未解析メッセージを送信することができます。  
  
## <a name="bredeployment-utility-cannot-deploy-or-undeploy-policies-if-a4swift-vocabularies-are-not-correctly-configured"></a>BREDeployment ユーティリティが展開または A4SWIFT ボキャブラリが正しく構成されていない場合は、ポリシーを展開解除することはできません。  
 A4SWIFT のビジネス ルール エンジン ポリシー BREDeployment.exe ツールを使用して展開を解除しようとする BREDeployment.exe 構成ファイルが適切なボキャブラリ ファイルの場所を指していない場合は、ツールは、エラーを報告可能性があります。 BREDeployment.exe 構成ファイルの場所を変更して、新しい場所にボキャブラリ ファイルが含まれていない場合、この問題があります。 ボキャブラリが見つからなかった構成ポリシーの展開または展開解除を停止することを知らせるエラーが表示されます。  
  
 この問題を解決するには、標準を使用して、**ビジネス ルール エンジン展開ウィザード**します。 UI の詳細については[!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-swift/known-issues5.md)