---
title: "BAM ポータルの既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e681e910-c664-479c-86f3-a6ae0ec97775
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0aa12d0f25a004f2e713f360e00c0f0c1192d304
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-in-the-bam-portal"></a>BAM ポータルでの既知の問題
このトピックでは、BAM ポータルの使用中に発生する可能性がある問題の特定と解決に役立つ情報を提供します。  
  
## <a name="errors-are-generated-when-the-bam-portal-and-internet-explorer-7-or-internet-explorer-8-are-on-the-same-computer-and-the-security-settings-are-set-to-low"></a>BAM ポータルと Internet Explorer 7 または Internet Explorer 8 が同じコンピューター上にあり、セキュリティの設定が [低] に設定されている場合に発生するエラー  
 **問題**  
  
 Internet Explorer 7 または Internet Explorer 7 または Internet Explorer 8 を使用するときに[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]、 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]エラー メッセージが発生する可能性があります**でサーバー エラー '/BAM' アプリケーション**次で状況:  
  
-   存在しないアクティビティ インスタンスを参照している関連アクティビティをクリックした場合  
  
-   ながらクリックすると、**警告の保存**次のシナリオでボタンをクリックします。  
  
    -   クエリを作成する、**アクティビティの検索**ページし、をクリックして**警告の設定**です。  
  
    -   警告フィールドに入力し、をクリックして**警告の保存**です。  
  
    -   [戻る] ボタンをクリックした。  
  
    -   クリックする、**警告の保存**を再度クリックします。  
  
 **原因**  
  
 [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] で、セキュリティ レベルを [低] に設定して Internet Explorer 7 または Internet Explorer 8 を実行している場合、Web 要求は低レベルの特権で実行されます。 Windows 統合セキュリティの問題に対応するために、Internet Explorer はユーザー トークンに対し、低レベルの特権しか渡しません。  
  
 BAM ポータルがインストールされているコンピューターと同じコンピューターで Internet Explorer を使用し、Internet Explorer のセキュリティ レベルが [低] に設定されている場合、ポータルは低いレベルの特権トークンを持つユーザーの権限を借用します。 このトークンには、イベント ログに書き込むためのアクセス許可がありません。 ポータルでエラーが発生すると、ポータルはイベント ログにそのエラーを記録しようとしますが、ユーザー トークンにはイベント ログにアクセスできる十分な権限がないため、操作は失敗します。  
  
 **解決策**  
  
 ローカル コンピューターから参照する必要がある場合は、信頼済みサイトに http://localhost を追加する必要があります。  
  
#### <a name="to-add-localhost-to-the-list-of-trusted-sites"></a>信頼済みサイトに localhost を追加するには  
  
1.  Internet Explorer で、をクリックして**ツール**、クリックして**インターネット オプション**です。  
  
2.  クリックして、**セキュリティ** タブをクリックして**信頼済みサイト**で、**を表示またはセキュリティ設定を変更するゾーンを選択して**ウィンドウです。  
  
3.  クリックして、**サイト**ボタンをクリックします。  
  
4.  **この web サイトをゾーンに追加**テキスト ボックスで、「 **http://localhost**です。 場合、**サーバーの確認 (https:) このゾーン内のすべてのサイトの**チェック ボックスがオン、オフにし、をクリックして、**追加**ボタンをクリックします。 サイト、http://localhost に表示されます、 **web サイト** ボックスの一覧です。  
  
5.  必要に応じて、復元、**サーバーの確認 (https:) このゾーン内のすべてのサイトの**を元の状態のチェック ボックスです。  
  
6.  クリックして、**閉じる**ボタンをクリックし、をクリックして**OK**です。  
  
## <a name="bam-portal-aggregations-do-not-populate-existing-data-when-using-an-ip-address-as-a-url-in-internet-explorer-7"></a>Internet Explorer 7 で IP アドレスを URL として使用すると、BAM ポータルの集計に既存のデータが表示されない  
 **問題**  
  
 Internet Explorer 7 または Internet Explorer 8 を URL として IP アドレスを使用する場合と[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]、 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]集計を BAM ポータルを表示するには、次のメッセージが表示します。"詳細なし。 クエリを実行できませんでした。"  
  
 **原因**  
  
 Internet Explorer 7 または Internet Explorer 8 の既定のセキュリティ設定では、IPv4 および IPv6 のアドレスを URL として使用してサイトにアクセスすることができません。  
  
 **解決策**  
  
 信頼済みサイトの一覧にサイト アドレスを追加し、ドメイン間でのデータ ソースのアクセスを有効にします。  
  
#### <a name="to-add-the-ip-address-to-the-trusted-sites-list"></a>信頼済みサイト一覧に IP アドレスを追加するには  
  
1.  Internet Explorer で、をクリックして**ツール**、クリックして**インターネット オプション**です。  
  
2.  クリックして、**セキュリティ** タブをクリックして、**信頼済みサイト**セキュリティ ゾーンです。  
  
3.  クリックして、**サイト**ボタンをクリックします。  
  
4.  **この web サイトをゾーンに追加**、BAM ポータルの IP アドレスを入力して、をクリックして**追加**です。  
  
5.  **[閉じる]**をクリックし、 **[OK]**をクリックします。  
  
#### <a name="to-enable-access-to-data-sources-across-domains"></a>ドメイン間でのデータ ソースのアクセスを有効にするには  
  
1.  Internet Explorer で、をクリックして**ツール**、クリックして**インターネット オプション**です。  
  
2.  クリックして、**セキュリティ** タブをクリックして、**信頼済みサイト**セキュリティ ゾーンです。  
  
3.  クリックして、**レベルのカスタマイズ**ボタンの下にスクロールすると、 **[その他]**のノード、**設定**ツリー。  
  
4.  **ドメイン間でデータ ソースにアクセス**ノード、をクリックして、**オプションを有効にする**ボタンをクリックし、をクリックして**[ok]**です。  
  
## <a name="bmexe-does-not-run-in-powershell"></a>BM.exe が PowerShell で実行されない  
 **問題**  
  
 次のコマンドを PowerShell で実行すると、エラーがスローされます。  
  
```  
bm.exe get-config -FileName:config.xml  
```  
  
 **原因**  
  
 PowerShell が、.exe ファイルおよび構成ファイルのパスを見つけることができませんでした。  
  
 **解決策**  
  
 PowerShell で bm.exe を使用する場合、.exe ファイルおよび構成ファイルの完全なパスを指定します。 例:`bm.exe get-config -FileName:config.xml`として指定する必要があります`“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`です。  
  
## <a name="see-also"></a>参照  
 [BAM ポータルの計画](../core/planning-for-the-bam-portal.md)