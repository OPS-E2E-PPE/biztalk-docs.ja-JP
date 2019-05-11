---
title: 不完全なアクティビティ インスタンスの解決 |Microsoft Docs
description: BizTalk Server で BAMPrimaryImport データベースのバックアップ後に BAM アクティビティ インスタンスがアクティブなまま
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
ms.openlocfilehash: 83510267108754985e9121bf473c25215b9a08a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334918"
---
# <a name="resolve-incomplete-bam-activity-instances---biztalk-server"></a>不完全な BAM アクティビティ インスタンスの BizTalk Server を解決します。
BAM では、不完全なアクティビティ インスタンスのデータを格納特別な*アクティブなインスタンス*BAMPrimaryImport データベースのテーブル。  
  
 インスタンス レコードの一部が前に開始、BAMPrimaryImport データベースの最後のバックアップ、バックアップ後に完了した、これらのレコードは、アクティブ インスタンス テーブルに残ります。 BAMPrimaryImport データベースを復元すると、これらのインスタンスの完了レコードは失われますためにです。  
  
 アクティブ インスタンス テーブル内のレコードが妨げられない BAM 正常に機能して、これらのレコードは「完了」としてマークしてから、アクティブなインスタンス テーブルから移動してお勧めします。  
  
## <a name="prerequisites"></a>前提条件  
BizTalk Server 管理者グループのメンバーとしてサインインします。  
  
## <a name="create-a-list-of-incomplete-activityids"></a>不完全な Activityid のリストを作成します。 
  
1.  BAMPrimaryImport データベースに対して次のクエリを実行します。  
  
    ```  
    Select ActivityID from bam_<ActivityName>_Active where IsComplete = 0  
    ```  
  
2.  外部システムからのデータは、アクティビティ インスタンスが実際に完了したことを示している場合は、インスタンスを手動で完了するのには、次のクエリを実行します。  
  
    ```  
    begin transaction
    exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
    commit transaction
    ```  
  
> [!NOTE]
>  置き換えることで、継続アクティビティを完了すると同じ手順を実行できる`ActivityID`で`ContinuationID`します。  
> 
>  メイン トレースは、アクティブな継続トレースがある、継続トレースが完了するまでにはアクティブです。  

## <a name="remove-incomplete-instances"></a>不完全なインスタンスを削除します。
不完全なアクティビティ インスタンスは、カスタム SQL スクリプトを使用して、BAMPrimaryImport データベースから削除することもできます。 参照してください[不完全なアクティビティ インスタンスを削除](how-to-remove-incomplete-activity-instances.md)サンプルについては、します。

## <a name="see-also"></a>参照  
 [BAM のバックアップと復元](../core/backing-up-and-restoring-bam.md)
