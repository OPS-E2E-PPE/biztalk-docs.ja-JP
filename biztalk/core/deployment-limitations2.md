---
title: "展開 Limitations2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deployment, limitations
- passwords, adapter limitations
ms.assetid: 9db2ca70-5db2-4b14-a898-13049737c188
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05fa9704823bd7e9df9f0bc7d4516719a8a490e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="0f830-102">展開の制限事項</span><span class="sxs-lookup"><span data-stu-id="0f830-102">Deployment Limitations</span></span>
<span data-ttu-id="0f830-103">アスタリスクでトランスポート アダプターのパスワードが格納されている (\*\*\*\*\*\*) が BizTalk 展開ウィザードによってエクスポートし、管理に渡されるバインド ファイルに同じ形式でコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="0f830-103">The Transport Adapter password is stored as asterisks (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Deployment Wizard, and is passed to the management component in the same format.</span></span> <span data-ttu-id="0f830-104">アスタリスクをランダムな英数字の値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="0f830-104">Edit the binding file before importing by replacing the asterisks with random alphanumeric values (that is, not the correct password).</span></span> <span data-ttu-id="0f830-105">使用して、正しいパスワードを入力し、**トランスポートのプロパティ**バインド ファイルをインポートした後のページです。</span><span class="sxs-lookup"><span data-stu-id="0f830-105">Then enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
 <span data-ttu-id="0f830-106">バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="0f830-106">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="0f830-107">このため、パスワード情報はクリア テキストでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="0f830-107">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="0f830-108">次回のバインド情報をインポートするファイルを使用するトランスポートのプロパティ ページのユーザー インターフェイスを使用してのパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f830-108">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="0f830-109">または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f830-109">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="0f830-110">この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f830-110">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f830-111">.Msi ファイルをインポートするときに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Enterprise アダプターのいずれかのバインド情報を含むアプリケーションをインポート エラー メッセージを受信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0f830-111">When importing an .msi file into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="0f830-112">サポートされている修正プログラムを Microsoft からのエラーの詳細と共に[http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us)です。</span><span class="sxs-lookup"><span data-stu-id="0f830-112">A supported hotfix is available from Microsoft along with a full description of the error at [http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us).</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="0f830-113">パスワードの制限への対処方法</span><span class="sxs-lookup"><span data-stu-id="0f830-113">Password Limitation Workaround</span></span>  
 <span data-ttu-id="0f830-114">パスワードの制限への対処方法として、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="0f830-114">Use one of the following as a work-around for the password limitation.</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="0f830-115">パスワードの制限の問題を回避するには</span><span class="sxs-lookup"><span data-stu-id="0f830-115">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="0f830-116">アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="0f830-116">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="0f830-117">これは、セキュリティ上の理由により推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="0f830-117">This is not recommended for security reasons.</span></span>  
  
2.  <span data-ttu-id="0f830-118">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="0f830-118">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="0f830-119">使用して、正しいパスワードを入力してください、**トランスポートのプロパティ**バインド ファイルをインポートした後のページです。</span><span class="sxs-lookup"><span data-stu-id="0f830-119">Enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0f830-120">この回避する場合のみ使用できます、ターゲット コンピューター上またはカスタム ツールを開発することにより、Microsoft Visual Studio がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="0f830-120">This work-around can be used only if Microsoft Visual Studio is installed on the target computer or by developing a custom tool.</span></span>  
  
 <span data-ttu-id="0f830-121">**- または -**</span><span class="sxs-lookup"><span data-stu-id="0f830-121">**-OR-**</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="0f830-122">パスワードの制限の問題を回避するには</span><span class="sxs-lookup"><span data-stu-id="0f830-122">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="0f830-123">パスワードではなく、エンタープライズ シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f830-123">Use Enterprise Single Sign-On instead of using passwords.</span></span>  
  
     <span data-ttu-id="0f830-124">SSO オプションを使用するために追加の作業は必要ありません。バインド ファイルをインポートするだけです。</span><span class="sxs-lookup"><span data-stu-id="0f830-124">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="0f830-125">論理システムと送信および受信サービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f830-125">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f830-126">参照</span><span class="sxs-lookup"><span data-stu-id="0f830-126">See Also</span></span>  
 <span data-ttu-id="0f830-127">[JD Edwards OneWorld トランスポートのプロパティを設定する方法](../core/how-to-set-jd-edwards-oneworld-transport-properties.md) </span><span class="sxs-lookup"><span data-stu-id="0f830-127">[How to Set JD Edwards OneWorld Transport Properties](../core/how-to-set-jd-edwards-oneworld-transport-properties.md) </span></span>  
 [<span data-ttu-id="0f830-128">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="0f830-128">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies4.md)