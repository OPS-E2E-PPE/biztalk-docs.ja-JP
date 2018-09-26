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
ms.openlocfilehash: 0533a1431ada4127e2b4746af19b0ccbaf4ecd39
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973075"
---
# <a name="known-issues-in-the-bam-portal"></a>BAM ポータルでの既知の問題
このトピックでは、BAM ポータルの使用中に発生する可能性がある問題の特定と解決に役立つ情報を提供します。  
  
## <a name="errors-occur-when-the-bam-portal-and-ie-are-on-the-same-computer-and-security-settings-are-low"></a>BAM ポータルと IE が同じコンピューター上とセキュリティ設定が低いときにエラーが発生します。  
 **問題**  
  
 Internet Explorer を使用する場合は、エラー メッセージが発生する可能性があります**でサーバー エラー '/BAM' アプリケーション**次の状況で。  
  
- 存在しないアクティビティ インスタンスを参照している関連アクティビティをクリックした場合  
  
- クリックして、**警告の保存**次のシナリオでのボタン。  
  
  -   クエリを作成する、**アクティビティの検索**ページし、クリックして**警告の設定**します。  
  
  -   アラートのフィールドをクリックした**警告の保存**します。  
  
  -   [戻る] ボタンをクリックした。  
  
  -   クリックする、**警告の保存**もう一度ボタンをクリックします。  
  
  **原因**  
  
  Web 要求を低に設定すると Internet Explorer を実行して、セキュリティ レベルでは、低レベルの特権で実行されます。 Windows 統合セキュリティの問題に対応するために、Internet Explorer はユーザー トークンに対し、低レベルの特権しか渡しません。  
  
  BAM ポータルがインストールされているコンピューターと同じコンピューターで Internet Explorer を使用し、Internet Explorer のセキュリティ レベルが [低] に設定されている場合、ポータルは低いレベルの特権トークンを持つユーザーの権限を借用します。 このトークンには、イベント ログに書き込むためのアクセス許可がありません。 ポータルでエラーが発生すると、ポータルはイベント ログにそのエラーを記録しようとしますが、ユーザー トークンにはイベント ログにアクセスできる十分な権限がないため、操作は失敗します。  
  
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
  
 Internet Explorer を URL として、IP アドレスを使用して、BAM ポータルを表示する、集計が表示されます、次のメッセージ:"詳細なし。 クエリを実行できませんでした。"  
  
 **原因**  
  
 Internet Explorer で、既定のセキュリティ設定は、IPv4 と IPv6 アドレスを Url として使用してサイトにアクセスを禁止する可能性があります。  
  
 **解決方法**  
  
 信頼済みサイトの一覧にサイト アドレスを追加し、ドメイン間でのデータ ソースのアクセスを有効にします。  
  
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
  
## <a name="bmexe-does-not-run-in-powershell"></a>BM.exe が PowerShell で実行されない  
 **問題**  
  
 次のコマンドを PowerShell で実行すると、エラーがスローされます。  
  
```  
bm.exe get-config -FileName:config.xml  
```  
  
 **原因**  
  
 PowerShell が、.exe ファイルおよび構成ファイルのパスを見つけることができませんでした。  
  
 **解決方法**  
  
 PowerShell で bm.exe を使用する場合、.exe ファイルおよび構成ファイルの完全なパスを指定します。 例:`bm.exe get-config -FileName:config.xml`として指定する必要があります`“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`します。  
  
## <a name="see-also"></a>参照  
 [BAM ポータルの計画](../core/planning-for-the-bam-portal.md)