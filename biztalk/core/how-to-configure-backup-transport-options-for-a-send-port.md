---
title: 送信ポートに対してバックアップ トランスポートのオプションを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, send ports
- managing [send ports], configuring
- configuring, backing up [send ports]
- managing [send ports], backup options
- send ports, configuring
- send ports, backup options
ms.assetid: f05f57a6-e62b-4640-a6e2-cb73e9de2a14
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ee35e6eb408ab8749e12a7747643783cabc3019
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341690"
---
# <a name="how-to-configure-backup-transport-options-for-a-send-port"></a>送信ポートに対してバックアップ トランスポートのオプションを構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートに対してバックアップ トランスポートのオプションを構成する方法を説明します。 指定したバックアップ トランスポートは、プライマリ トランスポートは、関数が失敗したイベントに反映されます。 プライマリ トランスポートの構成を記載[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)します。  
  
> [!NOTE]
>  動的ポートのプロパティがない構成のトランスポートのオプションは実行時に自動的に決定されるために使用できます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-specify-transport-options-for-a-send-port"></a>送信ポートに対してトランスポートのオプションを指定するには  
  
1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループと、送信ポートに対してバックアップ トランスポートのオプションを構成する BizTalk アプリケーションを展開します。  
  
3. 展開**送信ポート**、構成、 をクリックする送信ポートを右クリックして**プロパティ**、順にクリックします**バックアップ トランスポート**します。  
  
4. 次の表に示すように、バックアップ トランスポートのプロパティを構成し、 **OK**します。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**型**|ドロップダウン リストから、適切なバックアップ トランスポートの種類を選択するか、トランスポート プロトコル。 送信請求 - 応答のポートの場合、ドロップダウン リストでは、送信請求 - 応答をサポートするアダプターのみを選択できます。|  
   |**構成**|バックアップ トランスポートの種類を選択してクリックして**構成**、し、トランスポートのプロパティを構成します。 プロパティを構成する方法の詳細については、次のようにクリックします。**ヘルプ**します。|  
   |**送信ハンドラー**|ドロップダウン リストから、送信アダプターが動作しているホスト インスタンスを選択します。|  
   |**再試行の回数**|メッセージのエラーでメッセージを再送信する送信ポートの回数を指定します。 既定値は 3 です。許容範囲は 0 ~ 1,000 です。|  
   |**再試行の間隔**|メッセージの再送を試みる間隔を分単位で間隔を指定します。 既定値は 5 です。許容範囲は 0 ~ 525,600 です。|  
  
## <a name="see-also"></a>参照  
 [送信ポートの作成および構成](../core/creating-and-configuring-send-ports.md)