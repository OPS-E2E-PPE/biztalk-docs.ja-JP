---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 39b22cf6bf77f6e23b4a242e8c711070ef8a153c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530843"
---
# <a name="deployment-limitations"></a><span data-ttu-id="ea584-101">デプロイメントの制限事項</span><span class="sxs-lookup"><span data-stu-id="ea584-101">Deployment Limitations</span></span>
<span data-ttu-id="ea584-102">によってエクスポートされるバインド ファイルでトランスポート アダプターのパスワードが星 (\*) として格納されている、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、され、同じ形式で管理コンポーネントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="ea584-102">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span> <span data-ttu-id="ea584-103">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="ea584-103">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span>  
  
 <span data-ttu-id="ea584-104">バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="ea584-104">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="ea584-105">このため、パスワード情報はクリア テキストでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="ea584-105">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="ea584-106">次回のバインド情報をインポートするファイルを使用するトランスポートのプロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea584-106">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span>  
  
 <span data-ttu-id="ea584-107">または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea584-107">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="ea584-108">この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea584-108">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="ea584-109">パスワードの制限への対処方法</span><span class="sxs-lookup"><span data-stu-id="ea584-109">Password Limitation Workaround</span></span>  
 <span data-ttu-id="ea584-110">パスワードの制限を回避するには、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ea584-110">To work around the password limitation, you can do the following.</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="ea584-111">パスワードの制限を回避するには</span><span class="sxs-lookup"><span data-stu-id="ea584-111">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="ea584-112">パスワードではなく、エンタープライズ シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea584-112">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="ea584-113">SSO オプションを使用するために追加の作業は必要ありません。バインド ファイルをインポートするだけです。</span><span class="sxs-lookup"><span data-stu-id="ea584-113">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="ea584-114">論理システムと送信および受信サービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea584-114">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea584-115">参照</span><span class="sxs-lookup"><span data-stu-id="ea584-115">See Also</span></span>  
 [<span data-ttu-id="ea584-116">インポートの JD Edwards EnterpriseOne のアプリ</span><span class="sxs-lookup"><span data-stu-id="ea584-116">Import the JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)