---
title: 作成する方法、受信場所 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.createreceivelocation
helpviewer_keywords:
- receive locations, creating
- managing [receive locations], creating
- creating, receive locations
ms.assetid: ec0202cf-0e69-4ae2-aba6-8cd2c3c77e82
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe82afdc62a7ba2c10087c78a6a24c1722e5812a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249690"
---
# <a name="how-to-create-a-receive-location"></a>受信場所を作成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、新しい受信場所を作成し、その受信場所が属する受信ポートを指定する方法について説明します。 受信場所は、受信メッセージを受信するアドレスと、そのアドレスで受信したメッセージを処理するメッセージング パイプラインで構成されます。  
  
 受信場所を作成するには、作成する受信場所と同じ種類の受信ポートがこのアプリケーションに既に存在している必要があります。 受信ポートを作成する方法の詳細については、次を参照してください。[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)です。  
  
 作成できる受信場所の種類は次のとおりです。  
  
-   一方向 — メッセージを渡すだけで、応答を同期的に待機することの不要なアプリケーションに使用します。  
  
-   要求 - 応答 — メッセージに対する応答が必要なアプリケーションに使用します。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中に受信場所を作成するには、このトピックの手順を実行します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。 さらに、SSO データベースに対する適切なアクセス許可が必要です。  
  
### <a name="to-create-a-receive-location"></a>受信場所を作成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信場所を作成する BizTalk アプリケーションを展開します。  
  
3.  右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**または**要求-応答受信場所**に基づいたの種類を作成する場所を受信します。  
  
4.  受信ポートの選択 で 受信ポートをこの受信場所で、をクリックして をクリックして**OK**です。  
  
5.  **受信場所のプロパティ**ウィンドウで、次のように行い、クリックして**OK**:  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|受信場所の名前を入力します。|  
    |**型**|ドロップダウン リストから、トランスポートの種類またはトランスポート プロトコルを選択します。 トランスポートの種類を変更する場合、次に説明するように、トランスポートのプロパティを構成する必要があります。|  
    |**構成**|トランスポートの種類を選択してクリックして**構成**を表示する、**トランスポートのプロパティ** ダイアログ ボックスし、受信場所のアダプター プロパティを構成します。 手順についてをクリックして**ヘルプ** ダイアログ ボックス。 アダプターの種類ごとの構成の詳細については、下の該当するトピックを参照してください[を使用してアダプター](../core/using-adapters.md)です。|  
    |**受信ハンドラー**|ドロップダウン リストから、受信場所が動作する BizTalk Server ホストのインスタンスを選択します。 受信ハンドラーは、このホストで実行される必要があります。|  
    |**受信パイプライン**|ドロップダウン リストから、この受信場所でのメッセージの受信に使用する受信パイプラインを選択します。|  
    |**送信パイプライン**|ドロップダウン リストから、この受信場所からの応答の送信に使用する送信パイプラインを選択します。 この一覧は、受信場所が要求 - 応答の受信ポートに関連付けられている場合にのみ利用できます。|  
    |**ように、プライマリの場所**|1 つの受信ポートに対して複数の受信場所があり、この受信ポートで取引先など別のエンティティから自分の組織宛てのメッセージを受け取るときにこの受信場所を使用する場合は、このチェック ボックスをオンにします。 最初に作成した受信場所は、自動的にプライマリ受信場所として選択されます。 別の受信場所をプライマリとして指定しない限り、このプロパティは選択された状態で使用不可となります。|  
  
## <a name="see-also"></a>参照  
 [受信場所の管理](../core/managing-receive-locations.md)