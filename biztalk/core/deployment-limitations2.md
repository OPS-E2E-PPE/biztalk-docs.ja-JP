---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 64f202316e59040a77cb04da99857e8539a184ac
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="deployment-limitations"></a>展開の制限事項
アスタリスクでトランスポート アダプターのパスワードが格納されている (\*\*\*\*\*\*) が BizTalk 展開ウィザードによってエクスポートし、管理に渡されるバインド ファイルに同じ形式でコンポーネントです。 アスタリスクをランダムな英数字の値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力し、**トランスポートのプロパティ**バインド ファイルをインポートした後のページです。  
  
 バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。 このため、パスワード情報はクリア テキストでは表示されません。 次回のバインド情報をインポートするファイルを使用するトランスポートのプロパティ ページのユーザー インターフェイスを使用してのパスワードを入力する必要があります。 または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。 この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。  
  

## <a name="password-limitation-workaround"></a>パスワードの制限への対処方法  
 パスワードの制限への対処方法として、次のいずれかの方法を使用します。  
  
#### <a name="to-work-around-the-password-limitation"></a>パスワードの制限の問題を回避するには  
  
1.  アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。  
  
    > [!CAUTION]
    >  これは、セキュリティ上の理由により推奨されていません。  
  
2.  アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力してください、**トランスポートのプロパティ**バインド ファイルをインポートした後のページです。  
  
    > [!NOTE]
    >  この回避する場合のみ使用できます、ターゲット コンピューター上またはカスタム ツールを開発することにより、Microsoft Visual Studio がインストールされています。  
  
 **- または -**  
  
#### <a name="to-work-around-the-password-limitation"></a>パスワードの制限の問題を回避するには  
  
1.  パスワードではなく、エンタープライズ シングル サインオンを使用します。  
  
     SSO オプションを使用するために追加の作業は必要ありません。バインド ファイルをインポートするだけです。  
  
2.  論理システムと送信および受信サービスを確認します。  
  
## <a name="see-also"></a>参照  
 [BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [インポート JD Edwards OneWorld アプリ](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)