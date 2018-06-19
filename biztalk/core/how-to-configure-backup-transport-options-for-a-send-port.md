---
title: 送信ポートに対してバックアップ トランスポートのオプションを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 8ff8b1354772290ce9e04742a6130a6f6f2df627
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248378"
---
# <a name="how-to-configure-backup-transport-options-for-a-send-port"></a>送信ポートに対してバックアップ トランスポートのオプションを構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートに対してバックアップ トランスポートのオプションを構成する方法について説明します。 プライマリ トランスポートにエラーが発生した場合は、指定したバックアップ トランスポートが有効になります。 プライマリ トランスポートの構成に記載されて[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。  
  
> [!NOTE]
>  動的ポートの場合、トランスポート オプションは実行時に自動的に決まるため、プロパティを手動で構成することはできません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-specify-transport-options-for-a-send-port"></a>送信ポートのトランスポート オプションを指定するには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートに対してバックアップ トランスポートのオプションを構成する BizTalk アプリケーションを展開します。  
  
3.  展開**送信ポート**をクリックして、構成する送信ポートを右クリックして**プロパティ**、クリックして**バックアップ トランスポート**です。  
  
4.  次の表に示すようにバックアップ トランスポートのプロパティを構成し、をクリックして**OK**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**型**|ドロップダウン リストから、適切なバックアップ トランスポートの種類またはトランスポート プロトコルを選択します。 送信請求 - 応答のポートの場合、ドロップダウン リストでは、送信請求 - 応答をサポートするアダプターのみを選択できます。|  
    |**構成**|バックアップ トランスポートの種類を選択してクリックして**構成**、およびトランスポートのプロパティを構成します。 プロパティを構成する詳細についてをクリックして**ヘルプ**です。|  
    |**送信ハンドラー**|ドロップダウン リストから、送信アダプターが動作しているホスト インスタンスを選択します。|  
    |**再試行の回数**|メッセージ エラーが発生したときに送信ポートがメッセージを再送する回数を指定します。 指定できる範囲は 0 ～ 1,000 です。既定値は 3 です。|  
    |**再試行の間隔**|メッセージの再送を試みる間隔 (分) を指定します。 既定値は 5 です。許容範囲は 0 ~ 525,600 です。|  
  
## <a name="see-also"></a>参照  
 [作成して、送信ポートの構成](../core/creating-and-configuring-send-ports.md)