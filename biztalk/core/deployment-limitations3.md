---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: acc8560096423eb69b7cad8d9e6264707ae9a636
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="09987-101">展開の制限事項</span><span class="sxs-lookup"><span data-stu-id="09987-101">Deployment Limitations</span></span>

## <a name="overview"></a><span data-ttu-id="09987-102">概要</span><span class="sxs-lookup"><span data-stu-id="09987-102">Overview</span></span>
<span data-ttu-id="09987-103">トランスポート アダプターのパスワードは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によってエクスポートされるバインド ファイルにアスタリスク (******) で保存され、同じ形式で管理コンポーネントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="09987-103">The Transport Adapter password is stored as stars (******) in the binding file that is exported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span>  
  
 <span data-ttu-id="09987-104">バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="09987-104">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="09987-105">このため、パスワード情報はクリア テキストでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="09987-105">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="09987-106">次にファイルを使用してバインド情報をインポートするときに、トランスポート プロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09987-106">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="09987-107">または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="09987-107">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="09987-108">この場合、インポート操作が完了した後、バインド ファイルからパスワードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09987-108">In this case, you must delete the passwords from the binding file after the import operation finishes.</span></span>  
  

## <a name="password-limitation-workaround"></a><span data-ttu-id="09987-109">パスワードの制限への対処方法</span><span class="sxs-lookup"><span data-stu-id="09987-109">Password Limitation Workaround</span></span>  
 <span data-ttu-id="09987-110">このパスワードの制限に対処するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="09987-110">To work around this password limitation, you can use one of the following methods:</span></span>  
  
-   <span data-ttu-id="09987-111">アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="09987-111">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="09987-112">この操作は、セキュリティ上の理由により推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="09987-112">This practice is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="09987-113">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="09987-113">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="09987-114">使用して、正しいパスワードを入力してください、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページです。</span><span class="sxs-lookup"><span data-stu-id="09987-114">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="09987-115">この対処方法を使用できるのは、対象のコンピューターに Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] がインストールされているか、カスタム ツールを開発する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="09987-115">This work-around can be used only if Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] is installed on the target computer, or if you develop a custom tool.</span></span>  
  
 <span data-ttu-id="09987-116">-または-</span><span class="sxs-lookup"><span data-stu-id="09987-116">-or-</span></span>  
  
-   <span data-ttu-id="09987-117">パスワードではなく、エンタープライズ シングル サインオン (SSO) を使用します。</span><span class="sxs-lookup"><span data-stu-id="09987-117">Use Enterprise Single Sign-On (SSO) instead of using passwords.</span></span>  
  
     <span data-ttu-id="09987-118">SSO オプションを使用するには、バインド ファイルをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09987-118">Using the SSO option requires an import of the binding file.</span></span>  
  
 <span data-ttu-id="09987-119">論理システムと送信を確認し、サービスを受信します。</span><span class="sxs-lookup"><span data-stu-id="09987-119">Verify the logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09987-120">参照</span><span class="sxs-lookup"><span data-stu-id="09987-120">See Also</span></span>  
[<span data-ttu-id="09987-121">バインドのインポートと制限事項</span><span class="sxs-lookup"><span data-stu-id="09987-121">Import bindings & limitations</span></span>](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md)