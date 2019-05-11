---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: e32af9507ff3e7079bb6d1110f93439c90a19852
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393256"
---
# <a name="setting-peoplesoft-transport-properties"></a>PeopleSoft トランスポート プロパティの設定
PeopleSoft トランスポートのプロパティはデザインに使用し、実行時間。 **トランスポートのプロパティ**ダイアログ ボックスで、接続および資格情報パラメーターに固有の設定、サーバー システムとアクセスしようとしているオブジェクト。  
  
 ![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")  
  
### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  アダプターの必要なプロパティを展開し、PeopleSoft サーバーへの接続に必要なすべての情報を入力します。  
  
     Microsoft BizTalk Adapter for PeopleSoft Enterprise を PeopleSoft Enterprise に接続する構成パラメーターを設定する必要があります。 このデータは、大文字小文字を区別します。  
  
    |パラメーター|説明|  
    |---------------|-----------------|  
    |`Application Server Path`|ポートのロックを実行しているが、PeopleSoft Application Server がリッスンしているコンピューターを表す文字列。 PeopleSoft 8 Application への URL パスの構文は//< computer_name >:\<ポート\>します。 PeopleSoft 管理者に問い合わせて、\<ポート\>値。 \<ポート\>値は、JOLT プロトコル リスナー ポート、App Server ポートではありません。 既定の JOLT ポートは 9000 ですです。|  
    |`JAVA_HOME`|たとえば、JDK のインストール をポイントする JAVA_HOME 変数を設定します。**C:\j2sdk1.4.2_08**します。|  
    |`Password`|選択しなかった場合**使用 SSO**、BizTalk Adapter for PeopleSoft Enterprise サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。<br /><br /> PeopleSoft システムへのログオン ユーザーのパスワードを表す文字列。 文字は表示されませんが、アスタリスク (*) で表されます。|  
    |`PeopleSoft 8.x Jar Files`|コンポーネントを使用するには、インターフェイス (PeopleSoft 8 のみ)、クラスパスに含める、PeopleSoft コンポーネント インターフェイスを更新する必要があります jar ファイルを使用します。 例: **< PeopleSoft_Home > \web\PSJOA\psjoa.jar**します。|  
    |`User Name`|選択しなかった場合**使用 SSO**、BizTalk Adapter for PeopleSoft Enterprise サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。<br /><br /> PeopleSoft システムへのログオンに必要なユーザー名を表す文字列。|  
  
2.  入力、**追加パラメーター**値の日付をキーとして使用する場合に、別の形式があります。 YYYY-MM-DD では、既定の形式を示します。  
  
3.  入力、**同時実行制御**で呼び出し、たとえば 200 の数を表す値**最大同時呼び出し数**必要な場合。  
  
     **最大同時呼び出し数**パラメーターは、バック エンド サーバーは、データの量を処理できない場合に、オーバー ロードの保護をアクティブにします。 同時呼び出しは、対象のアダプターはまだありません返信要求です。 設定**最大同時呼び出し数**スループットがバックエンド処理機能を上回るインスタンスでします。  
  
     既定値のこのフィールドが-1 の場合に発生します保護れないことを意味します。  
  
     BizTalk Server 送信アダプターでは、要求を送信して、同時実行の数が呼び出しまたはの設定値を超える場合**最大同時呼び出し数**、同時呼び出しの数まで、要求が保存された送信スレッド設定値を下回るまで減少します。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft 送信ハンドラーの作成](../core/creating-peoplesoft-send-handlers.md)