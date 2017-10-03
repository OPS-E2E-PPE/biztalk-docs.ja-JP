---
title: "展開 Limitations3 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passwords, deployment limitations
- deployment, password limitations
- transport adapter password
ms.assetid: 79cd330f-ecc5-430e-9d79-608593d873cb
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae0d01947e0769189c269a1853e7fda0e11cedb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="4f613-102">展開の制限事項</span><span class="sxs-lookup"><span data-stu-id="4f613-102">Deployment Limitations</span></span>
<span data-ttu-id="4f613-103">トランスポート アダプターのパスワードは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によってエクスポートされるバインド ファイルにアスタリスク (******) で保存され、同じ形式で管理コンポーネントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="4f613-103">The Transport Adapter password is stored as stars (******) in the binding file that is exported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span>  
  
 <span data-ttu-id="4f613-104">バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="4f613-104">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="4f613-105">このため、パスワード情報はクリア テキストでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="4f613-105">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="4f613-106">次にファイルを使用してバインド情報をインポートするときに、トランスポート プロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f613-106">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="4f613-107">または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f613-107">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="4f613-108">この場合、インポート操作が完了した後、バインド ファイルからパスワードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f613-108">In this case, you must delete the passwords from the binding file after the import operation finishes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f613-109">.Msi ファイルをインポートするときに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Enterprise アダプターのいずれかのバインド情報を含むアプリケーションをインポート エラー メッセージを受信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f613-109">When importing an .msi file in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="4f613-110">サポートされている修正プログラムを Microsoft からのエラーの詳細と共に[http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087)です。</span><span class="sxs-lookup"><span data-stu-id="4f613-110">A supported hotfix is available from Microsoft along with a full description of the error at [http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087).</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="4f613-111">パスワードの制限への対処方法</span><span class="sxs-lookup"><span data-stu-id="4f613-111">Password Limitation Workaround</span></span>  
 <span data-ttu-id="4f613-112">このパスワードの制限に対処するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f613-112">To work around this password limitation, you can use one of the following methods:</span></span>  
  
-   <span data-ttu-id="4f613-113">アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="4f613-113">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="4f613-114">この操作は、セキュリティ上の理由により推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="4f613-114">This practice is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="4f613-115">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="4f613-115">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="4f613-116">使用して、正しいパスワードを入力してください、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページです。</span><span class="sxs-lookup"><span data-stu-id="4f613-116">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f613-117">この対処方法を使用できるのは、対象のコンピューターに Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] がインストールされているか、カスタム ツールを開発する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="4f613-117">This work-around can be used only if Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] is installed on the target computer, or if you develop a custom tool.</span></span>  
  
 <span data-ttu-id="4f613-118">-または-</span><span class="sxs-lookup"><span data-stu-id="4f613-118">-or-</span></span>  
  
-   <span data-ttu-id="4f613-119">パスワードではなく、エンタープライズ シングル サインオン (SSO) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f613-119">Use Enterprise Single Sign-On (SSO) instead of using passwords.</span></span>  
  
     <span data-ttu-id="4f613-120">SSO オプションを使用するには、バインド ファイルをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f613-120">Using the SSO option requires an import of the binding file.</span></span>  
  
 <span data-ttu-id="4f613-121">論理システムと送信を確認し、サービスを受信します。</span><span class="sxs-lookup"><span data-stu-id="4f613-121">Verify the logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f613-122">参照</span><span class="sxs-lookup"><span data-stu-id="4f613-122">See Also</span></span>  
 [<span data-ttu-id="4f613-123">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="4f613-123">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies5.md)