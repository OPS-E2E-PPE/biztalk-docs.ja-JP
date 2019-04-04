---
title: Analysis Services と BAM プライマリ インポート データベース間の暗号化を有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQL Server Analysis Services, enabling encryption
- Primary Import database [BAM], SQL Server Analysis Services
- Primary Import database [BAM], enabling encryption
- SQL Server Analysis Services, Primary Import database [BAM]
ms.assetid: 8107c557-e57c-4569-9ff7-abcb7a8e5243
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aedb10b8818e270164147c4f25d554c42b3d9ee2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005643"
---
# <a name="how-to-enable-encryption-between-analysis-services-and-the-bam-primary-import-database"></a><span data-ttu-id="4d97a-102">Analysis Services と BAM プライマリ インポート データベース間の暗号化を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="4d97a-102">How to Enable Encryption Between Analysis Services and the BAM Primary Import Database</span></span>
<span data-ttu-id="4d97a-103">既定では、BAM のインストールまたはアップグレード中、暗号化は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="4d97a-103">Encryption is not enabled by default during an installation or upgrade of BAM.</span></span> <span data-ttu-id="4d97a-104">暗号化を有効にするには、BAM 構成 XML ファイルの UseEncryption フラグの値を 1 に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d97a-104">To enable encryption, you must set the UseEncryption flag in the BAM configuration XML file to a value of 1.</span></span>  
  
 <span data-ttu-id="4d97a-105">また、SQL Server Analysis Services で暗号化を有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="4d97a-105">You must also enable encryption in SQL Server Analysis Services.</span></span> <span data-ttu-id="4d97a-106">暗号化を有効にする方法の詳細については、[Analysis Services インスタンスとクライアントの通信をセキュリティで保護する](http://go.microsoft.com/fwlink/?LinkId=190805)(http://go.microsoft.com/fwlink/?LinkId=190805)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d97a-106">For more information about enabling encryption, see [Securing Client Communication with an Analysis Services Instance](http://go.microsoft.com/fwlink/?LinkId=190805) (http://go.microsoft.com/fwlink/?LinkId=190805).</span></span>  
  
### <a name="to-enable-encryption-between-sql-server-analysis-services-and-the-bam-primary-import-database"></a><span data-ttu-id="4d97a-107">SQL Server Analysis Services と BAM プライマリ インポート データベース間の暗号化を有効にするには</span><span class="sxs-lookup"><span data-stu-id="4d97a-107">To enable encryption between SQL Server Analysis Services and the BAM Primary Import Database</span></span>  
  
1. <span data-ttu-id="4d97a-108">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="4d97a-108">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="4d97a-109">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4d97a-109">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
3. <span data-ttu-id="4d97a-110">型**bm config の取得のファイル名:\<出力ファイル\>** します。</span><span class="sxs-lookup"><span data-stu-id="4d97a-110">Type **bm get-config -FileName:\<output file\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4d97a-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d97a-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="4d97a-112">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4d97a-112">Press **ENTER**.</span></span>  
  
5. <span data-ttu-id="4d97a-113">エクスポートした構成ファイルをテキスト エディターで開き、UseEncryption プロパティ フラグの値を 1 に変更します。</span><span class="sxs-lookup"><span data-stu-id="4d97a-113">Open the file configuration file that you have exported in a text editor and change the value of the UseEncryption property flag to 1.</span></span>  
  
   -   <span data-ttu-id="4d97a-114">既定の設定:\<プロパティ名 ="UseEncryption"\>0\</Property\></span><span class="sxs-lookup"><span data-stu-id="4d97a-114">Default Setting: \<Property Name="UseEncryption"\>0\</Property\></span></span>  
  
   -   <span data-ttu-id="4d97a-115">新しい設定:\<プロパティ名 ="UseEncryption"\>1\</Property\></span><span class="sxs-lookup"><span data-stu-id="4d97a-115">New Setting: \<Property Name="UseEncryption"\>1\</Property\></span></span>  
  
6. <span data-ttu-id="4d97a-116">」と入力して、BAM 構成を更新**bm 更新プログラム構成ファイル名:\<config ファイル\>** します。</span><span class="sxs-lookup"><span data-stu-id="4d97a-116">Update the BAM configuration by typing **bm update-config -FileName:\<config file\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4d97a-117">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d97a-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d97a-118">参照</span><span class="sxs-lookup"><span data-stu-id="4d97a-118">See Also</span></span>  
 [<span data-ttu-id="4d97a-119">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="4d97a-119">BAM Management Utility</span></span>](../core/bam-management-utility.md)