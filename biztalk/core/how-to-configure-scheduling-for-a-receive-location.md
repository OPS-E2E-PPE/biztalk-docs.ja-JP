---
title: スケジュールを構成する方法、受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, receive locations
- managing [receive locations], scheduling
- scheduling, receive locations
- managing [receive locations], configuring
ms.assetid: 2653e1c3-ddbd-4d3f-be64-2a5fcd7cf267
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 724ac21972a49f64264217d4958b91539381f3a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002779"
---
# <a name="how-to-configure-scheduling-for-a-receive-location"></a>受信場所のスケジュールを構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、受信場所のスケジュール プロパティを構成する方法について説明します。 受信場所がメッセージの処理を開始および停止する日付を指定できます。 また、1 日の中で、受信場所がメッセージを処理する特定の時間を指定することもできます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-configure-scheduling-for-a-receive-location"></a>受信場所のスケジュールを構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、受信場所のスケジュールを構成する BizTalk アプリケーションを展開します。  
  
3. クリックして**受信場所**、受信場所を右クリックし、クリックして**プロパティ**します。  
  
4. 左側のウィンドウで次のようにクリックします。**スケジュール**次の表に示すようにスケジュール設定のプロパティを構成し、クリック**OK**します。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**開始日**|このチェック ボックスをオンにした後、プルダウンで表示されるカレンダーから、受信場所でメッセージの処理を開始する日付を選択します。 年を変更するには、表示されている年をクリックします。|  
   |**停止日**|このチェック ボックスをオンにした後、プルダウンで表示されるカレンダーから、受信場所でメッセージの処理を停止する日付を選択します。 このプロパティは省略可能です。 停止日を指定しない場合、受信場所は無効にされるまでアクティブなままです。|  
   |**サービス時間帯を有効にします。**|は、1 日の時間を指定し、指定の時間のみにメッセージを受信する受信場所を構成するには、このチェック ボックスをオン、**開始時刻と停止時刻**ボックス。 このチェック ボックスをオフにすると、受信場所ではいつでもメッセージを受信します。 既定値は False (オフ) です。|  
   |**[開始時刻]**|受信場所でメッセージの受信を開始する時刻を指定します。 このボックスは、使用可能な場合にのみ、**有効にするサービス時間帯** チェック ボックスをオンします。|  
   |**停止時刻**|受信場所でメッセージの受信を停止する時刻を指定します。 このボックスは、使用可能な場合にのみ、**有効にするサービス時間帯** チェック ボックスをオンします。|  
  
## <a name="see-also"></a>参照  
 [受信場所の管理](../core/managing-receive-locations.md)