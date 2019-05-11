---
title: バックアップおよびデータベースを復元するためのベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, maintaining
- restoring, best practices
- best practices, backing up
- backing up, restoring
- backing up, best practices
- maintaining, best practices
- best practices, restoring
ms.assetid: 649ca56b-3cc1-49ad-9f74-ba1521e65ee1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9ac2784a19a55d477f71c9b6542b7d46948d63f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529132"
---
# <a name="best-practices-for-backing-up-and-restoring-databases"></a><span data-ttu-id="24ce1-102">バックアップおよびデータベースを復元するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="24ce1-102">Best Practices for Backing Up and Restoring Databases</span></span>
<span data-ttu-id="24ce1-103">バックアップし、BizTalk Server データベースを復元できるように、次のベスト プラクティスを確認します。</span><span class="sxs-lookup"><span data-stu-id="24ce1-103">Review the following best practices to help ensure that you can backup and restore your BizTalk Server databases.</span></span>  
  
-   <span data-ttu-id="24ce1-104">**バックアップの作成し復元のストラテジし、それらをテストします。**</span><span class="sxs-lookup"><span data-stu-id="24ce1-104">**Develop backup and restore strategies and test them.**</span></span>  
  
     <span data-ttu-id="24ce1-105">適切なプランでは、ハードウェア障害により失われた場合にデータをすばやく回復できます。</span><span class="sxs-lookup"><span data-stu-id="24ce1-105">With a good plan, you can quickly recover your data if it is lost due to hardware failure.</span></span>  
  
-   <span data-ttu-id="24ce1-106">**ディスク領域を管理し、以前のバックアップ ファイルをアーカイブします。**</span><span class="sxs-lookup"><span data-stu-id="24ce1-106">**Manage disk space and archive previous backup files.**</span></span>  
  
     <span data-ttu-id="24ce1-107">BizTalk Server のバックアップ ジョブでは、ディスク領域を節約するために、これらのバックアップ ファイルを管理する必要があるために、期限切れのバックアップ ファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="24ce1-107">The Backup BizTalk Server job does not delete outdated backup files, so you need to manage those backup files to conserve disk space.</span></span> <span data-ttu-id="24ce1-108">データベースの新しい完全バックアップを作成すると、期限切れのバックアップ ファイルをプライマリ ディスク上の領域を解放するアーカイブ ストレージ デバイスを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24ce1-108">After you have created a new full backup of your databases, you should move the outdated backup files onto an archival storage device to reclaim space on the primary disk.</span></span>  
  
-   <span data-ttu-id="24ce1-109">**同じコンピューターまたはバックアップするにはディスク上のバックアップを格納しないでください。**</span><span class="sxs-lookup"><span data-stu-id="24ce1-109">**Do not store backups on the same computer or disk that you are backing up.**</span></span>  
  
     <span data-ttu-id="24ce1-110">元のデータを使用するコンピューターとは異なる、バックアップのコンピューターまたはディスクを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24ce1-110">You should specify a computer or disk for your backup that is different from the computer with the original data.</span></span> <span data-ttu-id="24ce1-111">それ以外の場合、失われますすべてのデータ、ハードウェアが失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="24ce1-111">Otherwise, you will lose all of your data if the hardware fails.</span></span>  
  
-   <span data-ttu-id="24ce1-112">**コピーを保持します。**</span><span class="sxs-lookup"><span data-stu-id="24ce1-112">**Retain copies.**</span></span>  
  
     <span data-ttu-id="24ce1-113">メディアの少なくとも 3 つのコピーを保持します。</span><span class="sxs-lookup"><span data-stu-id="24ce1-113">Keep at least three copies of the media.</span></span> <span data-ttu-id="24ce1-114">適切に管理された環境に少なくとも 1 つのコピーをオフサイトをしてください。</span><span class="sxs-lookup"><span data-stu-id="24ce1-114">Keep at least one copy off-site in a properly controlled environment.</span></span>  
  
-   <span data-ttu-id="24ce1-115">**試験的な復元を実行します。**</span><span class="sxs-lookup"><span data-stu-id="24ce1-115">**Perform trial restorations.**</span></span>  
  
     <span data-ttu-id="24ce1-116">ファイルが正しくバックアップすることを確認するには、1 か月に 1 回以上の復元を試用版を実行します。</span><span class="sxs-lookup"><span data-stu-id="24ce1-116">Perform a trial restoration at least once a month to verify that your files were properly backed up.</span></span> <span data-ttu-id="24ce1-117">試用版の復元、ソフトウェアが正しく機能していることを確認するときを表示しないハードウェアの問題を発見します。</span><span class="sxs-lookup"><span data-stu-id="24ce1-117">A trial restoration can uncover hardware problems that do not show up when you verify that your software is functioning properly.</span></span> <span data-ttu-id="24ce1-118">ハード ディスク失敗するかどうか、システムおよびデータベースを復元することを確認するまでは待機しません。</span><span class="sxs-lookup"><span data-stu-id="24ce1-118">Do not wait until your hard disk fails to see if you can restore your system and databases.</span></span>  
  
-   <span data-ttu-id="24ce1-119">**デバイスとメディアを保護します。**</span><span class="sxs-lookup"><span data-stu-id="24ce1-119">**Secure devices and media.**</span></span>  
  
     <span data-ttu-id="24ce1-120">記憶域デバイスとバックアップ メディアの両方をセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="24ce1-120">Secure both the storage device and the backup media.</span></span> <span data-ttu-id="24ce1-121">他のユーザーが管理者を別のサーバーにデータを復元することによって盗まれた媒体からデータにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="24ce1-121">It is possible for someone to access the data from a stolen medium by restoring the data to another server for which they are an administrator.</span></span>  
  
-   <span data-ttu-id="24ce1-122">**バックアップを監視し、プロセスを復元します。**</span><span class="sxs-lookup"><span data-stu-id="24ce1-122">**Monitor the backup and restore process.**</span></span>  
  
     <span data-ttu-id="24ce1-123">バックアップすることを確認し、復元処理が成功した、バックアップし、BizTalk Server を復元するために使用する SQL Server エージェント ジョブを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24ce1-123">To ensure that the backup and restore process was successful, you should monitor the SQL Server Agent jobs used to backup and restore BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24ce1-124">参照</span><span class="sxs-lookup"><span data-stu-id="24ce1-124">See Also</span></span>  
 [<span data-ttu-id="24ce1-125">BizTalk Server データベースのバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="24ce1-125">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)