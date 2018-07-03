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
ms.openlocfilehash: b73074cd4b644a3d57765a389ca4120f5b1d799b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979723"
---
# <a name="how-to-configure-backup-transport-options-for-a-send-port"></a>送信ポートに対してバックアップ トランスポートのオプションを構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートに対してバックアップ トランスポートのオプションを構成する方法について説明します。 プライマリ トランスポートにエラーが発生した場合は、指定したバックアップ トランスポートが有効になります。 プライマリ トランスポートの構成を記載[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)します。  
  
> [!NOTE]
>  動的ポートの場合、トランスポート オプションは実行時に自動的に決まるため、プロパティを手動で構成することはできません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-specify-transport-options-for-a-send-port"></a>送信ポートのトランスポート オプションを指定するには  
  
1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、送信ポートに対してバックアップ トランスポートのオプションを構成する BizTalk アプリケーションを展開します。  
  
3. 展開**送信ポート**、構成、 をクリックする送信ポートを右クリックして**プロパティ**、順にクリックします**バックアップ トランスポート**します。  
  
4. 次の表に示すように、バックアップ トランスポートのプロパティを構成し、 **OK**します。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**型**|ドロップダウン リストから、適切なバックアップ トランスポートの種類またはトランスポート プロトコルを選択します。 送信請求 - 応答のポートの場合、ドロップダウン リストでは、送信請求 - 応答をサポートするアダプターのみを選択できます。|  
   |**構成**|バックアップ トランスポートの種類を選択してクリックして**構成**、し、トランスポートのプロパティを構成します。 プロパティを構成する方法の詳細については、次のようにクリックします。**ヘルプ**します。|  
   |**送信ハンドラー**|ドロップダウン リストから、送信アダプターが動作しているホスト インスタンスを選択します。|  
   |**再試行の回数**|メッセージ エラーが発生したときに送信ポートがメッセージを再送する回数を指定します。 指定できる範囲は 0 ～ 1,000 です。既定値は 3 です。|  
   |**再試行の間隔**|メッセージの再送を試みる間隔 (分) を指定します。 既定値は 5 です。許容範囲は 0 ~ 525,600 です。|  
  
## <a name="see-also"></a>参照  
 [送信ポートの作成および構成](../core/creating-and-configuring-send-ports.md)