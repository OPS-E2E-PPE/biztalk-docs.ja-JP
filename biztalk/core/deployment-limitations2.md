---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 8a61c55439b5e5f8455b21e59fae06c559b5ff16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389521"
---
# <a name="deployment-limitations"></a>デプロイメントの制限事項
アスタリスクでトランスポート アダプターのパスワードが格納されている (\*\*\*\*\*\*) の管理に渡される BizTalk 展開ウィザードによってエクスポートされるバインド ファイルに同じ形式でのコンポーネントです。 アスタリスクをランダムな英数字の値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力し、**トランスポートのプロパティ**バインド ファイルをインポートした後のページ。  
  
 バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。 このため、パスワード情報はクリア テキストでは表示されません。 次回のバインド情報をインポートするファイルを使用するトランスポートのプロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。 または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。 この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。  
  

## <a name="password-limitation-workaround"></a>パスワードの制限への対処方法  
 パスワードの制限の解決策として、次のいずれかを使用します。  
  
#### <a name="to-work-around-the-password-limitation"></a>パスワードの制限を回避するには  
  
1. アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。  
  
   > [!CAUTION]
   >  これは、セキュリティ上の理由により推奨されていません。  
  
2. アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力、**トランスポートのプロパティ**バインド ファイルをインポートした後のページ。  
  
   > [!NOTE]
   >  この回避できる場合にのみ使用、ターゲット コンピューター上またはカスタム ツールを開発することで、Microsoft Visual Studio がインストールされています。  
  
   **- または -**  
  
#### <a name="to-work-around-the-password-limitation"></a>パスワードの制限を回避するには  
  
1.  パスワードではなく、エンタープライズ シングル サインオンを使用します。  
  
     SSO オプションを使用するために追加の作業は必要ありません。バインド ファイルをインポートするだけです。  
  
2.  論理システムと送信および受信サービスを確認します。  
  
## <a name="see-also"></a>参照  
 [BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [インポートの JD Edwards OneWorld アプリ](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)