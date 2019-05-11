---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-enterprise-message-service/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 44fa3a4b614e70b424b8d3b18d058cd8817cc705
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351843"
---
# <a name="deployment-limitations"></a><span data-ttu-id="f3f68-101">デプロイメントの制限事項</span><span class="sxs-lookup"><span data-stu-id="f3f68-101">Deployment Limitations</span></span>
<span data-ttu-id="f3f68-102">トランスポート アダプターのパスワードは、星として格納されます (\*\*\*\*\*\*)、BizTalk Server によってエクスポートされるバインド ファイルにされ、同じ管理コンポーネントに渡されます形式です。</span><span class="sxs-lookup"><span data-stu-id="f3f68-102">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Server, and it passes to the management component in the same format.</span></span> <span data-ttu-id="f3f68-103">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="f3f68-103">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="f3f68-104">使用して、正しいパスワードを入力、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページ。</span><span class="sxs-lookup"><span data-stu-id="f3f68-104">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
 <span data-ttu-id="f3f68-105">これは、既知の制限です。</span><span class="sxs-lookup"><span data-stu-id="f3f68-105">This is a known limitation.</span></span> <span data-ttu-id="f3f68-106">バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="f3f68-106">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="f3f68-107">このため、パスワード情報はクリア テキストでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f3f68-107">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="f3f68-108">次にファイルを使用してバインド情報をインポートするときに、トランスポート プロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3f68-108">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="f3f68-109">または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="f3f68-109">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="f3f68-110">この場合、インポート操作が正常に完了した後は、バインド ファイルからパスワードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3f68-110">In this case, you must delete the passwords from the binding file after the import operation successfully finishes.</span></span>  
  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="f3f68-111">パスワードの制限への対処方法</span><span class="sxs-lookup"><span data-stu-id="f3f68-111">Password Limitation Workaround</span></span>  
 <span data-ttu-id="f3f68-112">このパスワードの制限に対処するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3f68-112">To work around this password limitation, you can use one of the following methods:</span></span>  
  
-   <span data-ttu-id="f3f68-113">アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="f3f68-113">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f3f68-114">これは、セキュリティ上の理由により推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="f3f68-114">This is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="f3f68-115">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="f3f68-115">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="f3f68-116">使用して、正しいパスワードを入力、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページ。</span><span class="sxs-lookup"><span data-stu-id="f3f68-116">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3f68-117">この対処方法を使用できるのは、ターゲット コンピューターに Visual Studio がインストールされているか、カスタム ツールを開発する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="f3f68-117">This work-around can be used only if Visual Studio is installed on the target computer, or if you develop a custom tool.</span></span>  
  
-   <span data-ttu-id="f3f68-118">論理システムと送信および受信サービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="f3f68-118">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
