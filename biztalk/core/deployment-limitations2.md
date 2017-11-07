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
# <a name="deployment-limitations"></a><span data-ttu-id="42528-101">展開の制限事項</span><span class="sxs-lookup"><span data-stu-id="42528-101">Deployment Limitations</span></span>
<span data-ttu-id="42528-102">アスタリスクでトランスポート アダプターのパスワードが格納されている (\*\*\*\*\*\*) が BizTalk 展開ウィザードによってエクスポートし、管理に渡されるバインド ファイルに同じ形式でコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="42528-102">The Transport Adapter password is stored as asterisks (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Deployment Wizard, and is passed to the management component in the same format.</span></span> <span data-ttu-id="42528-103">アスタリスクをランダムな英数字の値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="42528-103">Edit the binding file before importing by replacing the asterisks with random alphanumeric values (that is, not the correct password).</span></span> <span data-ttu-id="42528-104">使用して、正しいパスワードを入力し、**トランスポートのプロパティ**バインド ファイルをインポートした後のページです。</span><span class="sxs-lookup"><span data-stu-id="42528-104">Then enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
 <span data-ttu-id="42528-105">バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="42528-105">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="42528-106">このため、パスワード情報はクリア テキストでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="42528-106">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="42528-107">次回のバインド情報をインポートするファイルを使用するトランスポートのプロパティ ページのユーザー インターフェイスを使用してのパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42528-107">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="42528-108">または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="42528-108">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="42528-109">この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42528-109">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  

## <a name="password-limitation-workaround"></a><span data-ttu-id="42528-110">パスワードの制限への対処方法</span><span class="sxs-lookup"><span data-stu-id="42528-110">Password Limitation Workaround</span></span>  
 <span data-ttu-id="42528-111">パスワードの制限への対処方法として、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="42528-111">Use one of the following as a work-around for the password limitation.</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="42528-112">パスワードの制限の問題を回避するには</span><span class="sxs-lookup"><span data-stu-id="42528-112">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="42528-113">アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="42528-113">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="42528-114">これは、セキュリティ上の理由により推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="42528-114">This is not recommended for security reasons.</span></span>  
  
2.  <span data-ttu-id="42528-115">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="42528-115">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="42528-116">使用して、正しいパスワードを入力してください、**トランスポートのプロパティ**バインド ファイルをインポートした後のページです。</span><span class="sxs-lookup"><span data-stu-id="42528-116">Enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="42528-117">この回避する場合のみ使用できます、ターゲット コンピューター上またはカスタム ツールを開発することにより、Microsoft Visual Studio がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="42528-117">This work-around can be used only if Microsoft Visual Studio is installed on the target computer or by developing a custom tool.</span></span>  
  
 <span data-ttu-id="42528-118">**- または -**</span><span class="sxs-lookup"><span data-stu-id="42528-118">**-OR-**</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="42528-119">パスワードの制限の問題を回避するには</span><span class="sxs-lookup"><span data-stu-id="42528-119">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="42528-120">パスワードではなく、エンタープライズ シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="42528-120">Use Enterprise Single Sign-On instead of using passwords.</span></span>  
  
     <span data-ttu-id="42528-121">SSO オプションを使用するために追加の作業は必要ありません。バインド ファイルをインポートするだけです。</span><span class="sxs-lookup"><span data-stu-id="42528-121">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="42528-122">論理システムと送信および受信サービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="42528-122">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42528-123">参照</span><span class="sxs-lookup"><span data-stu-id="42528-123">See Also</span></span>  
 <span data-ttu-id="42528-124">[BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="42528-124">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="42528-125">インポート JD Edwards OneWorld アプリ</span><span class="sxs-lookup"><span data-stu-id="42528-125">Import the JD Edwards OneWorld app</span></span>](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)