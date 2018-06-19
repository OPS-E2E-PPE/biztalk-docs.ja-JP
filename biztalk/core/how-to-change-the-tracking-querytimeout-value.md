---
title: 追跡 QueryTimeout 値を変更する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: ca9f61466323e0b154bdeb0499cc5cee6e4ef10c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247474"
---
# <a name="how-to-change-the-tracking-querytimeout-value"></a>追跡 QueryTimeout 値の変更方法
既定では、クエリの実行時間が 60 秒を超えると、メッセージとサービス インスタンスの追跡はタイムアウトになります。 レジストリでタイムアウトの値を変更することで、60 秒より長くクエリを実行できます。  
  
> [!CAUTION]
>  レジストリの編集を誤ると、システムに深刻な悪影響を及ぼす可能性があります。 レジストリを変更する前に、コンピューター上のすべての重要なデータをバックアップしておくことをお勧めします。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-change-the-query-timeout-value"></a>クエリのタイムアウト値を変更するには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリック**ok**です。  
  
2.  レジストリ エディターで、次のサブキーを探してクリックします。  
  
     **Hkey_local_machine \software\microsoft\biztalk server \3.0**  
  
3.  Tracking サブキーがある場合は、手順 6. へ進みます。  
  
4.  Tracking サブキーを作成する、**編集** メニューのをポイント**新規**、順にクリック**キー**です。  
  
5.  型**追跡**、ENTER キーを押します。  
  
6.  次のサブキーを探してクリックします。  
  
     **Hkey_local_machine Server\3.0\Tracking**  
  
7.  **編集** メニューのをポイント**新規**、クリックして**DWORD 値**です。  
  
8.  型**ConnectionTimeout**、ENTER キーを押します。  
  
9. 右クリック**ConnectionTimeout**、クリックして**変更**です。  
  
10. **DWORD 値の編集**ダイアログ ボックスで、をクリックして**Decimal**です。  
  
11. **値のデータ**ボックスには、クエリのタイムアウト値を設定し、をクリックする秒単位で値を入力**OK**です。  
  
12. **[ファイル]** メニューの **[終了]** をクリックします。  
  
    > [!NOTE]
    >  新しいタイムアウト値を有効にするには、BizTalk Server 管理コンソールを閉じて再び開くことが必要になる場合があります。  
  
## <a name="see-also"></a>参照  
 [履歴および追跡データを表示します。](../core/viewing-historical-and-tracked-data.md)