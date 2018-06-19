---
redirect_url: /biztalk/core/architecture-of-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: a277c5f5588a9455119b96f7c600dbadccffb8ac
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014537"
---
# <a name="peoplesoft-enterprise-requirements"></a>PeopleSoft Enterprise の要件

## <a name="send-handler-requirements"></a>送信ハンドラーの要件  
 Microsoft BizTalk Adapter for PeopleSoft Enterprise にはカスタム コンポーネント インターフェイス (CI) が提供されているので、Java API を使用してアクセスすることができます。 PeopleSoft ツールを使用して PeopleSoft システムにカスタム CI オブジェクトの `GET_CI_INFO` を配置し、BizTalk Adapter for PeopleSoft Enterprise に必要なメタデータ情報を提供します。 詳細については、次を参照してください。[エンタープライズ アプリケーションのインストール アダプター](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)です。  
  
 1 回は、カスタム コンポーネント インターフェイスをアップロードします。 この `GET_CI_INFO.pc` ファイルで製品をインストールします。アダプターで CI を参照するには、このファイルがインストールされている必要があります。 PeopleSoft アプリケーション デザイナにアクセスする必要があります。 Application Designer アプリケーションは、BizTalk Server コンピューター上に存在する必要はありません。 Application Designer を使用して、参照する PeopleSoft コンピューターにカスタム CI をアップロードします。  
  
 環境変数 CLASSPATH を設定する必要がありますのでから PeopleSoft コンピューターにアクセスする必要があります (情報を設定または、**トランスポートのプロパティ**画面) を PeopleSoft の指す`PSJOA/psjoa.jar`ファイル。  
  
## <a name="see-also"></a>参照  
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   
 