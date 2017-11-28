---
title: "展開 Limitations4 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passwords, deployment limitations
- deployment, limitations
ms.assetid: 1312627e-9de2-461e-a8c4-66a9d41bb714
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2d8e33c7274ab0f95c6d7fff1bf9746ac86e420
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="2b945-102">展開の制限事項</span><span class="sxs-lookup"><span data-stu-id="2b945-102">Deployment Limitations</span></span>
<span data-ttu-id="2b945-103">によってエクスポートされるバインド ファイル (*) の星トランスポート アダプターのパスワードが格納されている、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、され、同じ形式で管理コンポーネントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="2b945-103">The Transport Adapter password is stored as stars (******) in the binding file that is exported by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span> <span data-ttu-id="2b945-104">アスタリスクを無効な値 (つまり、正しくないパスワード) に置き換えて、インポート前にバインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="2b945-104">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span>  
  
 <span data-ttu-id="2b945-105">バインド情報をエクスポートしても、生成されるバインド ファイルには、受信場所/送信ポートでトランスポート アダプターが使用したパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="2b945-105">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="2b945-106">このため、パスワード情報はクリア テキストでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2b945-106">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="2b945-107">次回のバインド情報をインポートするファイルを使用するトランスポートのプロパティ ページのユーザー インターフェイスを使用してのパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b945-107">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span>  
  
 <span data-ttu-id="2b945-108">または、パスワードをバインド ファイルに入力することで、インポート前にバインド ファイルを一時的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b945-108">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="2b945-109">この場合、インポート操作が正常に完了した後、バインド ファイルからパスワードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b945-109">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b945-110">.Msi ファイルをインポートするときに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Enterprise アダプターのいずれかのバインド情報を含むアプリケーションをインポート エラー メッセージを受信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b945-110">When importing an .msi file in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="2b945-111">サポートされている修正プログラムを Microsoft からのエラーの詳細と共に[http://go.microsoft.com/fwlink/?LinkId=196087](http://go.microsoft.com/fwlink/?LinkId=196087)です。</span><span class="sxs-lookup"><span data-stu-id="2b945-111">A supported hotfix is available from Microsoft along with a full description of the error at [http://go.microsoft.com/fwlink/?LinkId=196087](http://go.microsoft.com/fwlink/?LinkId=196087).</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="2b945-112">パスワードの制限への対処方法</span><span class="sxs-lookup"><span data-stu-id="2b945-112">Password Limitation Workaround</span></span>  
 <span data-ttu-id="2b945-113">パスワードの制限を回避するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b945-113">To work around the password limitation, you can do the following.</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="2b945-114">パスワードの制限の問題を回避するには</span><span class="sxs-lookup"><span data-stu-id="2b945-114">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="2b945-115">パスワードではなく、エンタープライズ シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="2b945-115">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="2b945-116">SSO オプションを使用するために追加の作業は必要ありません。バインド ファイルをインポートするだけです。</span><span class="sxs-lookup"><span data-stu-id="2b945-116">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="2b945-117">論理システムと送信および受信サービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="2b945-117">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b945-118">参照</span><span class="sxs-lookup"><span data-stu-id="2b945-118">See Also</span></span>  
 [<span data-ttu-id="2b945-119">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="2b945-119">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies3.md)