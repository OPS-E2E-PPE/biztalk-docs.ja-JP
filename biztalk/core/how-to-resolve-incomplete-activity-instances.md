---
title: "不完全なアクティビティ インスタンスを解決する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- instances, incomplete [BAM]
- restoring, BAM
- Primary Import database [BAM], incomplete instances
- restoring [BAM], Primary Import database
- Primary Import database [BAM], restoring
- BAM, restoring
ms.assetid: 8adbcb66-58ad-42c5-ba16-7dc07572099e
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81df9ee8b004a2dbd4a672eecb4f34894421a432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-incomplete-activity-instances"></a>不完全なアクティビティ インスタンスを解決する方法
BAM では、不完全なアクティビティ インスタンスのデータを格納特殊な*アクティブ インスタンス*BAMPrimaryImport データベースのテーブルにします。  
  
 インスタンス レコードの一部が開始し、BAMPrimaryImport データベースの最後のバックアップの前に、バックアップ後に、これらのレコードはアクティブ インスタンス テーブルに残ります。 これは、BAMPrimaryImport データベースが復元された後、これらのインスタンスの完了レコードが失われるからです。  
  
 アクティブ インスタンス テーブルに残ったレコードが、BAM の正常な機能を阻害することはありませんが、これらのレコードは "完了" としてマークし、アクティブ インスタンス テーブルから取り除くことをお勧めします。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-generate-a-list-of-incomplete-activityids-for-an-activity"></a>特定のアクティビティに対する不完全な ActivityID を検索するには  
  
1.  BAMPrimaryImport データベースに対し、次のクエリを実行します。  
  
    ```  
    Select ActivityID from bam_<ActivityName>_Active where IsComplete = 0  
    ```  
  
2.  外部システムからデータがアクティビティのインスタンスが実際に完了したことを示している場合は、インスタンスを手動で完了する次のクエリを実行します。  
  
    ```  
    exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
    ```  
  
> [!NOTE]
>  ActivityID を ContinuationID に置き換えることにより、同様の手順で、継続アクティビティを完了させることができます。  
  
> [!NOTE]
>  アクティブな継続トレースがメイン トレースに存在した場合、メイン トレースは、その継続トレースが完了するまでアクティブな状態のままとなります。  
  
## <a name="see-also"></a>参照  
 [バックアップおよび BAM を復元します。](../core/backing-up-and-restoring-bam.md)