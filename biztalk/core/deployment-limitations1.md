---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-enterprise-message-service/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: b669c06c5c474d5ce134b593dcecd110c6e8d572
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="7fe79-101">展開の制限事項</span><span class="sxs-lookup"><span data-stu-id="7fe79-101">Deployment Limitations</span></span>
<span data-ttu-id="7fe79-102">個の星トランスポート アダプターのパスワードが格納されている (\*\*\*\*\*\*) BizTalk Server によってエクスポートされるバインド ファイルにされ、同じ管理コンポーネントに渡されます形式です。</span><span class="sxs-lookup"><span data-stu-id="7fe79-102">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Server, and it passes to the management component in the same format.</span></span> <span data-ttu-id="7fe79-103">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="7fe79-103">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="7fe79-104">使用して、正しいパスワードを入力してください、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページです。</span><span class="sxs-lookup"><span data-stu-id="7fe79-104">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
 <span data-ttu-id="7fe79-105">これは、既知の制限です。</span><span class="sxs-lookup"><span data-stu-id="7fe79-105">This is a known limitation.</span></span> <span data-ttu-id="7fe79-106">バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="7fe79-106">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="7fe79-107">このため、パスワード情報はクリア テキストでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7fe79-107">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="7fe79-108">次にファイルを使用してバインド情報をインポートするときに、トランスポート プロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fe79-108">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="7fe79-109">または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="7fe79-109">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="7fe79-110">この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fe79-110">In this case, you must delete the passwords from the binding file after the import operation successfully finishes.</span></span>  
  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="7fe79-111">パスワードの制限への対処方法</span><span class="sxs-lookup"><span data-stu-id="7fe79-111">Password Limitation Workaround</span></span>  
 <span data-ttu-id="7fe79-112">このパスワードの制限に対処するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="7fe79-112">To work around this password limitation, you can use one of the following methods:</span></span>  
  
-   <span data-ttu-id="7fe79-113">アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="7fe79-113">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7fe79-114">これは、セキュリティ上の理由により推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="7fe79-114">This is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="7fe79-115">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="7fe79-115">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="7fe79-116">使用して、正しいパスワードを入力してください、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページです。</span><span class="sxs-lookup"><span data-stu-id="7fe79-116">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fe79-117">この対処方法を使用できるのは、対象のコンピューターに Visual Studio がインストールされているか、カスタム ツールを開発する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="7fe79-117">This work-around can be used only if Visual Studio is installed on the target computer, or if you develop a custom tool.</span></span>  
  
-   <span data-ttu-id="7fe79-118">論理システムと送信および受信サービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="7fe79-118">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
