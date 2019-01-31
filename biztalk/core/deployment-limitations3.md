---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 9d12874ef6042580183f407afc811a9d7f6e0fc9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009867"
---
# <a name="deployment-limitations"></a>デプロイメントの制限事項

## <a name="overview"></a>概要
トランスポート アダプターのパスワードは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によってエクスポートされるバインド ファイルにアスタリスク (******) で保存され、同じ形式で管理コンポーネントに渡されます。  
  
 バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。 このため、パスワード情報はクリア テキストでは表示されません。 次にファイルを使用してバインド情報をインポートするときに、トランスポート プロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。 または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。 この場合、インポート操作が完了した後、バインド ファイルからパスワードを削除する必要があります。  
  

## <a name="password-limitation-workaround"></a>パスワードの制限への対処方法  
 このパスワードの制限に対処するには、次のいずれかの方法を使用します。  
  
- アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。  
  
  > [!CAUTION]
  >  この操作は、セキュリティ上の理由により推奨されていません。  
  
- アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。 使用して、正しいパスワードを入力、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページ。  
  
  > [!NOTE]
  >  この対処方法を使用できるのは、ターゲット コンピューターに Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] がインストールされているか、カスタム ツールを開発する場合のみです。  
  
  - または -  
  
- パスワードではなく、エンタープライズ シングル サインオン (SSO) を使用します。  
  
   SSO オプションを使用するには、バインド ファイルをインポートする必要があります。  
  
  論理システムと送信を確認し、サービスを受信します。  
  
## <a name="see-also"></a>参照  
[バインドのインポートと制限事項](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md)