---
title: 不完全なアクティビティ インスタンスを解決するには |Microsoft ドキュメント
description: BAM アクティビティ インスタンスが BizTalk Server で BAMPrimaryImport データベースをバックアップした後アクティブなまま
ms.custom: ''
ms.date: 01/17/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8adbcb66-58ad-42c5-ba16-7dc07572099e
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 616ba096062da7ede8d78122e5a6faaca2befdc4
ms.sourcegitcommit: 20d33d8b74bf129a8d1a506ac4a1ad960184966d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2018
ms.locfileid: "27873418"
---
# <a name="resolve-incomplete-bam-activity-instances---biztalk-server"></a>不完全な BAM アクティビティ インスタンスを解決するには、BizTalk Server
BAM では、不完全なアクティビティ インスタンスのデータを格納特殊な *アクティブなインスタンス* BAMPrimaryImport データベースのテーブルです。  
  
 インスタンス レコードの一部では、BAMPrimaryImport データベースの最後のバックアップする前に開始は、バックアップ後に完了することが、これらのレコードはアクティブ インスタンス テーブルに残ります。 これは、BAMPrimaryImport データベースが復元された後、これらのインスタンスの完了レコードが失われるからです。  
  
 アクティブ インスタンス テーブルに残ったレコードが、BAM の正常な機能を阻害することはありませんが、これらのレコードは "完了" としてマークし、アクティブ インスタンス テーブルから取り除くことをお勧めします。  
  
## <a name="prerequisites"></a>前提条件  
BizTalk Server 管理者グループのメンバーとしてサインインします。  
  
## <a name="create-a-list-of-incomplete-activityids"></a>不完全な activityid 検索リストを作成します。 
  
1.  BAMPrimaryImport データベースに対し、次のクエリを実行します。  
  
    ```  
    Select ActivityID from bam_<ActivityName>_Active where IsComplete = 0  
    ```  
  
2.  外部システムからデータには、アクティビティ インスタンスが実際に完了したことが示されている場合は、インスタンスを手動で完了するには、以下のクエリを実行します。  
  
    ```  
    begin transaction
    exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
    commit transaction
    ```  
  
> [!NOTE]
>  置き換えることにより、継続アクティビティを完了する同じ処理を行うことができる`ActivityID`で`ContinuationID`です。  
> 
>  アクティブな継続トレースがメイン トレースに存在した場合、メイン トレースは、その継続トレースが完了するまでアクティブな状態のままとなります。  

## <a name="remove-incomplete-instances"></a>不完全なインスタンスを削除します。
不完全なアクティビティ インスタンスは、カスタムの SQL スクリプトを使用して、BAMPrimaryImport データベースから削除することもできます。 参照してください[不完全なアクティビティ インスタンスを削除する](how-to-remove-incomplete-activity-instances.md)サンプルについてはします。

## <a name="see-also"></a>参照  
 [BAM のバックアップと復元](../core/backing-up-and-restoring-bam.md)
