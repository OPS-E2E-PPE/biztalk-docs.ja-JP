---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 1772a30ce5496a3a14866da168a56958bc3bc78c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974096"
---
# <a name="setting-peoplesoft-transport-properties"></a>PeopleSoft トランスポート プロパティの設定
PeopleSoft トランスポートのプロパティは、設計時および実行時に使用されます。 **トランスポートのプロパティ**ダイアログ ボックスで、パラメーターを設定する接続と資格情報を特定サーバーのシステムおよびアクセスしようとしているオブジェクトにします。  
  
 ![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")  
  
### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  [アダプターに必要なプロパティ] を展開し、PeopleSoft サーバーへの接続に必要なすべての情報を入力します。  
  
     Microsoft BizTalk Adapter for PeopleSoft Enterprise を PeopleSoft Enterprise に接続するには、構成パラメーターを設定する必要があります。 このデータは、大文字と小文字が区別されます。  
  
    |パラメーター|Description|  
    |---------------|-----------------|  
    |`Application Server Path`|PeopleSoft Application Server が動作して受信を待ち受けているコンピューターおよびポートを表す文字列。 PeopleSoft 8 Application への URL パスの構文は//< computer_name >:\<ポート\>です。 PeopleSoft 管理者に問い合わせて、\<ポート\>値。 \<ポート\>値は、JOLT プロトコル リスナー ポート、App Server ポートではありません。 既定の JOLT ポートは 9000 です。|  
    |`JAVA_HOME`|たとえば、JDK インストールを指すように JAVA_HOME 変数を設定します。 **C:\j2sdk1.4.2_08**です。|  
    |`Password`|選択しなかった場合**SSO を使用する**、BizTalk Adapter for PeopleSoft Enterprise サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。<br /><br /> PeopleSoft システムへのログオンに使用するユーザーのパスワードを表す文字列です。 文字は表示されませんが、アスタリスク (*) で表されます。|  
    |`PeopleSoft 8.x Jar Files`|コンポーネント インターフェイス (PeopleSoft 8 のみ) を使用するには、PeopleSoft Component Interface の jar ファイルが含まれるように CLASSPATH を更新する必要があります 例: **< PeopleSoft_Home > \web\PSJOA\psjoa.jar**です。|  
    |`User Name`|選択しなかった場合**SSO を使用する**、BizTalk Adapter for PeopleSoft Enterprise サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。<br /><br /> PeopleSoft システムへのログオンに必要なユーザー名を表す文字列です。|  
  
2.  入力、**追加パラメーター**日付がキーとして使用するときの値とは別の形式です。 既定の形式は YYYY-MM-DD です。  
  
3.  入力、**同時実行制御**で呼び出し、たとえば 200 の数を表す値**Max Concurrent Calls**必要がある場合。  
  
     **Max Concurrent Calls**パラメーターは、バック エンド サーバーがデータの量を処理できない場合に、オーバー ロードの保護をアクティブにします。 同時呼び出しとは、アダプターがまだ返信を受信していない要求のことです。 設定**Max Concurrent Calls**場合、スループットがバックエンドの処理能力を超えています。  
  
     このフィールドの既定値は -1 です。保護は発生しません。  
  
     BizTalk Server が送信アダプターに要求を送信し、同時実行の数が呼び出しまたはに設定された値を超えて 場合**Max Concurrent Calls**、同時呼び出しの数まで、要求を保存送信スレッド設定された値以下に低下します。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft 送信ハンドラーの作成](../core/creating-peoplesoft-send-handlers.md)