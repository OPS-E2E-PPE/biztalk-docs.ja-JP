---
redirect_url: /biztalk/core/architecture-of-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 3db930f26e9c8a1d460f29c502d841ac27fd6c8e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314506"
---
# <a name="peoplesoft-enterprise-requirements"></a>PeopleSoft Enterprise の要件

## <a name="send-handler-requirements"></a>送信ハンドラーの要件  
 Microsoft BizTalk Adapter for PeopleSoft Enterprise では、カスタム コンポーネント インターフェイス (CI) が含まれていて、Java API を介してアクセスを提供します。 カスタム CI オブジェクトの`GET_CI_INFO`で BizTalk Adapter for PeopleSoft Enterprise のために必要なメタデータ情報を提供する PeopleSoft ツールを使用して PeopleSoft システムにデプロイされます。 詳細については、次を参照してください。[エンタープライズ アプリケーションのインストールのアダプター](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)します。  
  
 1 回は、カスタム コンポーネント インターフェイスをアップロードします。 このファイルは、`GET_CI_INFO.pc`製品がインストールされ、Ci を参照するアダプターを使用する前にインストールされている必要があります。 PeopleSoft アプリケーション デザイナにアクセスする必要があります。 Application Designer アプリケーションは、BizTalk Server コンピューター上に存在する必要はありません。 アプリケーション デザイナーを使用して、参照する PeopleSoft コンピューターにカスタム CI をアップロードします。  
  
 環境変数 CLASSPATH を設定する必要がありますので、PeopleSoft コンピューターへのアクセスが必要 (またはその情報を設定、**トランスポートのプロパティ**画面) を PeopleSoft の指す`PSJOA/psjoa.jar`ファイル。  
  
## <a name="see-also"></a>参照  
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   
 