---
title: "展開 Limitations1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: deployment, limitations
ms.assetid: a984ccce-37b2-4738-b652-7232a18e0510
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e65fb1c1a1211865b07c3abb987f0a1d31fbfd69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="74745-102">展開の制限事項</span><span class="sxs-lookup"><span data-stu-id="74745-102">Deployment Limitations</span></span>
<span data-ttu-id="74745-103">個の星トランスポート アダプターのパスワードが格納されている (\*\*\*\*\*\*) BizTalk Server によってエクスポートされるバインド ファイルにされ、同じ管理コンポーネントに渡されます形式です。</span><span class="sxs-lookup"><span data-stu-id="74745-103">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Server, and it passes to the management component in the same format.</span></span> <span data-ttu-id="74745-104">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="74745-104">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="74745-105">使用して、正しいパスワードを入力してください、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページです。</span><span class="sxs-lookup"><span data-stu-id="74745-105">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
 <span data-ttu-id="74745-106">これは、既知の制限です。</span><span class="sxs-lookup"><span data-stu-id="74745-106">This is a known limitation.</span></span> <span data-ttu-id="74745-107">バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="74745-107">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="74745-108">このため、パスワード情報はクリア テキストでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="74745-108">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="74745-109">次にファイルを使用してバインド情報をインポートするときに、トランスポート プロパティ ページのユーザー インターフェイスを使用してパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74745-109">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="74745-110">または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="74745-110">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="74745-111">この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74745-111">In this case, you must delete the passwords from the binding file after the import operation successfully finishes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74745-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションでエンタープライズ アダプターのバインド情報を含む .msi ファイルをインポートするときに、インポート エラー メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="74745-112">When importing an .msi file in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="74745-113">サポートされている修正プログラムを Microsoft からのエラーの詳細と共に[http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087)です。</span><span class="sxs-lookup"><span data-stu-id="74745-113">A supported hotfix is available from Microsoft along with a full description of the error at [http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087).</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="74745-114">パスワードの制限への対処方法</span><span class="sxs-lookup"><span data-stu-id="74745-114">Password Limitation Workaround</span></span>  
 <span data-ttu-id="74745-115">このパスワードの制限に対処するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="74745-115">To work around this password limitation, you can use one of the following methods:</span></span>  
  
-   <span data-ttu-id="74745-116">アスタリスクをプレーンテキストに置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="74745-116">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="74745-117">これは、セキュリティ上の理由により推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="74745-117">This is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="74745-118">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="74745-118">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="74745-119">使用して、正しいパスワードを入力してください、**トランスポートのプロパティ**バインド ファイルをインポートした後は、BizTalk Server 管理コンソール内のページです。</span><span class="sxs-lookup"><span data-stu-id="74745-119">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74745-120">この対処方法を使用できるのは、対象のコンピューターに Visual Studio がインストールされているか、カスタム ツールを開発する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="74745-120">This work-around can be used only if Visual Studio is installed on the target computer, or if you develop a custom tool.</span></span>  
  
-   <span data-ttu-id="74745-121">論理システムと送信および受信サービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="74745-121">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74745-122">参照</span><span class="sxs-lookup"><span data-stu-id="74745-122">See Also</span></span>  
 [<span data-ttu-id="74745-123">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="74745-123">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies2.md)