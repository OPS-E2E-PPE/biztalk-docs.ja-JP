---
title: BAM 管理ユーティリティを使用して BAM 構成ファイルを取得する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67ce5e0c-467a-486c-8eec-217a2a26d7b4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef0f4802aa44a042f39adbdc9f169b11a16796d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972280"
---
# <a name="how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a><span data-ttu-id="cb373-102">BAM 管理ユーティリティを使用して BAM 構成ファイルを取得する方法</span><span class="sxs-lookup"><span data-stu-id="cb373-102">How to Retrieve the BAM Configuration File Using the BAM Management Utility</span></span>
<span data-ttu-id="cb373-103">管理者および開発者は、BAM 管理ユーティリティを使用して、BAM インフラストラクチャの現在の構成を取得できます。</span><span class="sxs-lookup"><span data-stu-id="cb373-103">Administrators and developers can use the BAM Management utility to retrieve the current configuration of the BAM infrastructure.</span></span> <span data-ttu-id="cb373-104">取得した構成を使用すると、BAM のインストールを新しいサーバーに移行したり、既存の BAM を更新したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb373-104">The retrieved configuration can be used to migrate a BAM installation to a new server or it can be modified and used to update an existing BAM installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cb373-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="cb373-105">Prerequisites</span></span>  
 <span data-ttu-id="cb373-106">このトピックの手順を実行するための前提条件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cb373-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="cb373-107">構成済みの BAM データベース</span><span class="sxs-lookup"><span data-stu-id="cb373-107">Configured BAM databases</span></span>  
  
-   <span data-ttu-id="cb373-108">BAM プライマリ インポート データベースに対する読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="cb373-108">Permissions to read the BAM Primary Import database</span></span>  
  
### <a name="to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a><span data-ttu-id="cb373-109">BAM 管理ユーティリティを使用して BAM 構成ファイルを取得するには</span><span class="sxs-lookup"><span data-stu-id="cb373-109">To retrieve the BAM configuration file using the BAM Management utility</span></span>  
  
1.  <span data-ttu-id="cb373-110">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="cb373-110">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="cb373-111">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="cb373-111">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="cb373-112">コマンド ライン プロンプトで、次を入力: **bm get config ファイル名:\<出力ファイル\>** ここで、 \<*出力ファイル*\>は置き換えられます、BAM 構成ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="cb373-112">Type the following at the command line prompt: **bm get-config -FileName:\<output file\>**, where \<*output file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="cb373-113">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cb373-113">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb373-114">参照</span><span class="sxs-lookup"><span data-stu-id="cb373-114">See Also</span></span>  
 [<span data-ttu-id="cb373-115">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="cb373-115">BAM Management Utility</span></span>](../core/bam-management-utility.md)