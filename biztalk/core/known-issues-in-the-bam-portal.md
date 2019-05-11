---
title: BAM ポータルの既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e681e910-c664-479c-86f3-a6ae0ec97775
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a6eb2c711b654f5541c2c8fb7c42540b9210eb8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380954"
---
# <a name="known-issues-in-the-bam-portal"></a>BAM ポータルでの既知の問題
このトピックでには、特定し、BAM ポータルを使用しているときに発生する可能性がある問題を解決するのに役立つ情報が含まれています。  
  
## <a name="errors-occur-when-the-bam-portal-and-ie-are-on-the-same-computer-and-security-settings-are-low"></a>BAM ポータルと IE が同じコンピューター上とセキュリティ設定が低いときにエラーが発生します。  
 **問題**  
  
 Internet Explorer を使用する場合は、エラー メッセージが発生する可能性があります**でサーバー エラー '/BAM' アプリケーション**次の状況で。  
  
- ながら、存在しないアクティビティ インスタンスを指す関連アクティビティをクリックします。  
  
- クリックして、**警告の保存**次のシナリオでのボタン。  
  
  -   クエリを作成する、**アクティビティの検索**ページし、クリックして**警告の設定**します。  
  
  -   アラートのフィールドをクリックした**警告の保存**します。  
  
  -   [戻る] ボタンをクリックします。  
  
  -   クリックする、**警告の保存**もう一度ボタンをクリックします。  
  
  **原因**  
  
  Web 要求を低に設定すると Internet Explorer を実行して、セキュリティ レベルでは、低レベルの特権で実行されます。 Windows 統合セキュリティの問題を満たすためには、Internet Explorer は低レベルの特権でのユーザー トークンを渡します。  
  
  優先度を低セキュリティを Internet Explorer で設定すると、BAM ポータルがインストールされているものと同じコンピューターに Internet Explorer を使用して、ポータルは、低レベルの特権トークンを使用してユーザーを偽装します。 このトークンには、イベント ログに書き込むアクセス許可がありません。 ポータルには、エラーが発生すると、イベント ログにログを記録しようし、ユーザー トークンの権限は、イベント ログへのアクセスには不十分なために失敗します。  
  
  **解決方法**  
  
  追加するかどうかは、ローカル コンピューターから参照する必要があります、 http://localhost信頼済みサイトの一覧にします。  
  
#### <a name="add-localhost-to-the-list-of-trusted-sites"></a>Localhost を信頼済みサイトの一覧に追加します。  
  
1.  Internet Explorer で、次のようにクリックします。**ツール**、 をクリックし、**インターネット オプション**します。  
  
2.  をクリックして、**セキュリティ**タブをクリックし、をクリックし、**信頼済みサイト**で、**を表示またはセキュリティ設定を変更するゾーンを選択**ウィンドウ。  
  
3.  をクリックして、**サイト**ボタンをクリックします。  
  
4.  **この web サイトをゾーンに追加**テキスト ボックスに「  **http://localhost**します。 場合、**サーバーの確認が必要です (https:) すべてのサイトでこのゾーン** チェック ボックスをオン、オフにし、をクリックし、**追加**ボタン。 サイト、 http://localhostに表示されます、 **Websites**一覧。  
  
5.  必要に応じて、復元、**サーバーの確認 (https:) すべてのサイトでこのゾーン**を元の状態のチェック ボックス。  
  
6.  をクリックして、**閉じる**ボタンをクリックし、をクリックし、 **OK**します。  
  
## <a name="bam-portal-aggregations-do-not-populate-existing-data-when-using-an-ip-address-as-a-url-in-internet-explorer"></a>ユーザーは Internet Explorer で URL として IP アドレスを使用する場合は、Bam ポータルの集計には既存のデータは設定されません。
 **問題**  
  
 Internet Explorer を URL として、IP アドレスを使用して、BAM ポータルを表示する、集計、次のメッセージが表示されます。"詳細なし。 クエリ処理できませんでした。"  
  
 **原因**  
  
 Internet Explorer で、既定のセキュリティ設定は、IPv4 と IPv6 アドレスを Url として使用してサイトにアクセスを禁止する可能性があります。  
  
 **解決方法**  
  
 信頼済みサイト一覧に、サイトのアドレスを追加し、ドメイン間でデータ ソースへのアクセスを有効にします。  
  
#### <a name="add-the-ip-address-to-the-trusted-sites-list"></a>信頼済みサイト一覧に IP アドレスを追加します。  
  
1.  Internet Explorer で、次のようにクリックします。**ツール**、 をクリックし、**インターネット オプション**します。  
  
2.  をクリックして、**セキュリティ**タブをクリックし、をクリックし、**信頼済みサイト**セキュリティ ゾーンです。  
  
3.  をクリックして、**サイト**ボタンをクリックします。  
  
4.  **この web サイトをゾーンに追加**、BAM ポータルの IP アドレスを入力して、クリックして、**追加**します。  
  
5.  **[閉じる]** をクリックし、 **[OK]** をクリックします。  
  
#### <a name="enable-access-to-data-sources-across-domains"></a>ドメイン間でデータ ソースへのアクセスを有効にします。  
  
1.  Internet Explorer で、次のようにクリックします。**ツール**、 をクリックし、**インターネット オプション**します。  
  
2.  をクリックして、**セキュリティ**タブをクリックし、をクリックし、**信頼済みサイト**セキュリティ ゾーンです。  
  
3.  をクリックして、**レベルのカスタマイズ**ボタンの下にスクロールすると、 **[その他]** のノード、**設定**ツリー。  
  
4.  **ドメイン間でデータ ソースにアクセス**ノード、をクリックして、**オプションを有効にする**ボタンをクリックし、をクリックし、 **[ok]** します。  
  
## <a name="bmexe-does-not-run-in-powershell"></a>BM.exe が PowerShell で実行されません。  
 **問題**  
  
 次のコマンドは、PowerShell で実行するとエラーをスローします。  
  
```  
bm.exe get-config -FileName:config.xml  
```  
  
 **原因**  
  
 PowerShell は、.exe および構成ファイルのパスを特定できませんでした。  
  
 **解決方法**  
  
 PowerShell で bm.exe を使用する場合は、.exe および構成ファイルの完全なパスを指定します。 例:`bm.exe get-config -FileName:config.xml`として指定する必要があります`“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`します。  
  
## <a name="see-also"></a>参照  
 [BAM ポータルの計画](../core/planning-for-the-bam-portal.md)