---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 847e66c189cb8fc14014691f95d78b6eec4b45dc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013361"
---
# <a name="deployment-limitations"></a><span data-ttu-id="d3ea9-101">展開の制限事項</span><span class="sxs-lookup"><span data-stu-id="d3ea9-101">Deployment Limitations</span></span>
<span data-ttu-id="d3ea9-102">によってエクスポートされるバインド ファイル (\*) の星トランスポート アダプターのパスワードが格納されている、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、され、同じ形式で管理コンポーネントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="d3ea9-102">The Transport Adapter password is stored as stars (******) in the binding file that is exported by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span> <span data-ttu-id="d3ea9-103">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="d3ea9-103">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span>  
  
 <span data-ttu-id="d3ea9-104">バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="d3ea9-104">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="d3ea9-105">このため、パスワード情報はクリア テキストでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="d3ea9-105">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="d3ea9-106">次回のバインド情報をインポートするファイルを使用するトランスポートのプロパティ ページのユーザー インターフェイスを使用してのパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3ea9-106">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span>  
  
 <span data-ttu-id="d3ea9-107">または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="d3ea9-107">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="d3ea9-108">この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3ea9-108">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="d3ea9-109">パスワードの制限への対処方法</span><span class="sxs-lookup"><span data-stu-id="d3ea9-109">Password Limitation Workaround</span></span>  
 <span data-ttu-id="d3ea9-110">パスワードの制限を回避するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d3ea9-110">To work around the password limitation, you can do the following.</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="d3ea9-111">パスワードの制限の問題を回避するには</span><span class="sxs-lookup"><span data-stu-id="d3ea9-111">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="d3ea9-112">パスワードではなく、エンタープライズ シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3ea9-112">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="d3ea9-113">SSO オプションを使用するために追加の作業は必要ありません。バインド ファイルをインポートするだけです。</span><span class="sxs-lookup"><span data-stu-id="d3ea9-113">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="d3ea9-114">論理システムと送信および受信サービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="d3ea9-114">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ea9-115">参照</span><span class="sxs-lookup"><span data-stu-id="d3ea9-115">See Also</span></span>  
 [<span data-ttu-id="d3ea9-116">インポート JD Edwards EnterpriseOne アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d3ea9-116">Import the JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)