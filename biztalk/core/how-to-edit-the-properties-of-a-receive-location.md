---
title: "プロパティを編集する方法、受信場所 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [receive locations], properties
- managing [receive locations], editing
- receive locations, properties
- receive locations, editing
- editing, receive locations
- editing, properties
ms.assetid: 2b622050-a875-4896-bed6-65ca39a26dd3
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 578c5e2970e587180a7928563ebdd942c62dc396
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-edit-the-properties-of-a-receive-location"></a>受信場所のプロパティを編集する方法
このトピックでは、BizTalk Server 管理コンソールを使用して既存の受信場所のプロパティを編集する方法について説明します。 受信場所の作成方法の詳細については、次を参照してください。[受信場所を作成する方法](../core/how-to-create-a-receive-location.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-edit-the-properties-of-a-receive-location"></a>受信場所のプロパティを編集するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループと受信場所のプロパティを編集し、をクリックする BizTalk アプリケーション展開**受信場所**です。  
  
3.  右側のウィンドウで、受信場所を右クリックし、をクリックして**プロパティ**です。  
  
4.  **受信場所のプロパティ** ウィンドウでは、次のプロパティの 1 つ以上を編集し、をクリックして**OK**:  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|受信場所の名前を入力します。|  
    |**型**|ドロップダウン リストから、トランスポートの種類またはトランスポート プロトコルを選択します。 トランスポートの種類を変更する場合、次に説明するように、トランスポートのプロパティを構成する必要があります。|  
    |**構成**|トランスポートの種類を選択してクリックして**構成**を表示する、**トランスポートのプロパティ** ダイアログ ボックスし、受信場所のアダプター プロパティを構成します。 手順についてをクリックして**ヘルプ** ダイアログ ボックス。 アダプターの種類ごとの構成の詳細については、下の該当するトピックを参照してください[を使用してアダプター](../core/using-adapters.md)です。|  
    |**受信ハンドラー**|ドロップダウン リストから、受信場所が動作する BizTalk Server ホストのインスタンスを選択します。 受信ハンドラーは、このホストで実行される必要があります。|  
    |**受信パイプライン**|ドロップダウン リストから、この受信場所でのメッセージの受信に使用する受信パイプラインを選択します。|  
    |**送信パイプライン**|ドロップダウン リストから、この受信場所からの応答の送信に使用する送信パイプラインを選択します。 この一覧は、受信場所が要求 - 応答の受信ポートに関連付けられている場合にのみ利用できます。|  
    |**ように、プライマリの場所**|1 つの受信ポートに対して複数の受信場所があり、この受信ポートで取引先など別のエンティティから自分の組織宛てのメッセージを受け取るときにこの受信場所を使用する場合は、このチェック ボックスをオンにします。 最初に作成した受信場所は、自動的にプライマリ受信場所として選択されます。 別の受信場所をプライマリとして指定しない限り、このプロパティは選択された状態で使用不可となります。|  
  
> [!NOTE]
>  受信場所を変更した場合は、変更した受信場所に対応する分離ホストのワーカー プロセスを再起動します。  
  
## <a name="see-also"></a>参照  
 [受信場所の管理](../core/managing-receive-locations.md)