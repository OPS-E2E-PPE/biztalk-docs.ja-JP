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
# <a name="peoplesoft-enterprise-requirements"></a><span data-ttu-id="69eb3-101">PeopleSoft Enterprise の要件</span><span class="sxs-lookup"><span data-stu-id="69eb3-101">PeopleSoft Enterprise Requirements</span></span>

## <a name="send-handler-requirements"></a><span data-ttu-id="69eb3-102">送信ハンドラーの要件</span><span class="sxs-lookup"><span data-stu-id="69eb3-102">Send Handler requirements</span></span>  
 <span data-ttu-id="69eb3-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise にはカスタム コンポーネント インターフェイス (CI) が提供されているので、Java API を使用してアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="69eb3-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise contains a custom component interface (CI) and provides access to it through a Java API.</span></span> <span data-ttu-id="69eb3-104">PeopleSoft ツールを使用して PeopleSoft システムにカスタム CI オブジェクトの `GET_CI_INFO` を配置し、BizTalk Adapter for PeopleSoft Enterprise に必要なメタデータ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="69eb3-104">A custom CI object, `GET_CI_INFO`, is deployed in the PeopleSoft system using PeopleSoft Tools to provide metadata information that is required by BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="69eb3-105">詳細については、次を参照してください。[エンタープライズ アプリケーションのインストール アダプター](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="69eb3-105">For more information, see [Install Enterprise Applications adapters](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md).</span></span>  
  
 <span data-ttu-id="69eb3-106">1 回は、カスタム コンポーネント インターフェイスをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="69eb3-106">Uploading the custom component interface is a one-time occurrence.</span></span> <span data-ttu-id="69eb3-107">この `GET_CI_INFO.pc` ファイルで製品をインストールします。アダプターで CI を参照するには、このファイルがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69eb3-107">This file, `GET_CI_INFO.pc`, installs with the product and must be installed before you can use the adapter to browse CIs.</span></span> <span data-ttu-id="69eb3-108">PeopleSoft アプリケーション デザイナにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69eb3-108">You must have access to the PeopleSoft Application Designer.</span></span> <span data-ttu-id="69eb3-109">Application Designer アプリケーションは、BizTalk Server コンピューター上に存在する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="69eb3-109">The Application Designer application does not have to be on the BizTalk Server computer.</span></span> <span data-ttu-id="69eb3-110">Application Designer を使用して、参照する PeopleSoft コンピューターにカスタム CI をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="69eb3-110">You use the Application Designer to upload the custom CI onto the PeopleSoft computer that you browse.</span></span>  
  
 <span data-ttu-id="69eb3-111">環境変数 CLASSPATH を設定する必要がありますのでから PeopleSoft コンピューターにアクセスする必要があります (情報を設定または、**トランスポートのプロパティ**画面) を PeopleSoft の指す`PSJOA/psjoa.jar`ファイル。</span><span class="sxs-lookup"><span data-stu-id="69eb3-111">You must have access to the PeopleSoft computer because you must set the environment variable CLASSPATH (or set the information in the **Transport Properties** screen) to point to PeopleSoft's `PSJOA/psjoa.jar` file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69eb3-112">参照</span><span class="sxs-lookup"><span data-stu-id="69eb3-112">See Also</span></span>  
 [<span data-ttu-id="69eb3-113">作業の開始</span><span class="sxs-lookup"><span data-stu-id="69eb3-113">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   
 