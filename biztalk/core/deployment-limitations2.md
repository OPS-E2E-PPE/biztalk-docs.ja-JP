---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 314bffd50e152c1e3141e4f644c60bdbe7a3824a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011035"
---
# <a name="deployment-limitations"></a>デプロイメントの制限事項
アスタリスクでトランスポート アダプターのパスワードが格納されている (\*\*\*\*\*\*) の管理に渡される BizTalk 展開ウィザードによってエクスポートされるバインド ファイルに同じ形式でのコンポーネントです。 アスタリスクをランダムな英数字の値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力し、**トランスポートのプロパティ**バインド ファイルをインポートした後のページ。  
  
 バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。 このため、パスワード情報はクリア テキストでは表示されません。 次回のバインド情報をインポートするファイルを使用するトランスポートのプロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。 または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。 この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。  
  

## <a name="password-limitation-workaround"></a>パスワードの制限への対処方法  
 パスワードの制限への対処方法として、次のいずれかの方法を使用します。  
  
#### <a name="to-work-around-the-password-limitation"></a>パスワードの制限の問題を回避するには  
  
1. アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。  
  
   > [!CAUTION]
   >  これは、セキュリティ上の理由により推奨されていません。  
  
2. アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力、**トランスポートのプロパティ**バインド ファイルをインポートした後のページ。  
  
   > [!NOTE]
   >  この回避できる場合にのみ使用、ターゲット コンピューター上またはカスタム ツールを開発することで、Microsoft Visual Studio がインストールされています。  
  
   **- または -**  
  
#### <a name="to-work-around-the-password-limitation"></a>パスワードの制限の問題を回避するには  
  
1.  パスワードではなく、エンタープライズ シングル サインオンを使用します。  
  
     SSO オプションを使用するために追加の作業は必要ありません。バインド ファイルをインポートするだけです。  
  
2.  論理システムと送信および受信サービスを確認します。  
  
## <a name="see-also"></a>参照  
 [BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [インポートの JD Edwards OneWorld アプリ](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)