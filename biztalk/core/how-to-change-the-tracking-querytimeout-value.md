---
title: 追跡 QueryTimeout 値を変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [HAT], time-out limits
- HAT, time-out limits
ms.assetid: abc26f37-6537-42fa-81ff-bc8b758b4e10
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77e609b5b551fc5b8c97dac704ad31e4e413426c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387018"
---
# <a name="how-to-change-the-tracking-querytimeout-value"></a>追跡 QueryTimeout 値を変更する方法
既定では、メッセージとサービス インスタンスの追跡はタイムアウト場合は 60 秒を超えるクエリを実行します。 60 秒より長く実行するクエリを有効にするレジストリでタイムアウト値を変更することができます。  
  
> [!CAUTION]
>  レジストリの編集を誤ると、システムに深刻な悪影響を及ぼす可能性があります。 レジストリを変更する前に、コンピューター上のすべての重要なデータをバックアップしておくことをお勧めします。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-change-the-query-timeout-value"></a>クエリのタイムアウト値を変更するには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリックします**OK**します。  
  
2.  レジストリ エディターを見つけて次のサブキーを見つけてクリックします。  
  
     **Hkey_local_machine \software\microsoft\biztalk server \3.0**  
  
3.  Tracking サブキーがある場合は、手順 6 に進みます。  
  
4.  Tracking サブキーを作成する、**編集**メニューで、**新規**、 をクリックし、**キー**。  
  
5.  型**追跡**、し、ENTER キーを押します。  
  
6.  見つけて次のサブキーを見つけてクリックします。  
  
     **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\Tracking**  
  
7.  **編集**メニューで、**新規**、 をクリックし、 **DWORD 値**。  
  
8.  型**ConnectionTimeout**、し、ENTER キーを押します。  
  
9. 右クリックして**ConnectionTimeout**、 をクリックし、**変更**します。  
  
10. **DWORD 値の編集**ダイアログ ボックスで、をクリックして**Decimal**。  
  
11. **値データ**ボックスに、クエリのタイムアウト値を設定し、クリックする秒単位で値を入力**OK**します。  
  
12. **[ファイル]** メニューの **[終了]** をクリックします。  
  
    > [!NOTE]
    >  閉じて、新しいタイムアウト値の順序で BizTalk Server 管理コンソールを有効にする必要があります。  
  
## <a name="see-also"></a>参照  
 [履歴および追跡データの表示](../core/viewing-historical-and-tracked-data.md)