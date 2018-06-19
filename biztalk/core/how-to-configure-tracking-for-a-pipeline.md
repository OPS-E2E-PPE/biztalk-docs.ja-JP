---
title: 有効にするパイプラインの追跡 |Microsoft ドキュメント
description: メッセージ本文の追跡とパイプラインが BizTalk Server でメッセージを処理するときにイベント
ms.custom: ''
ms.date: 12/13/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f7f3c4a-4464-4170-a580-b4ce9296a097
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ed836947ff47e21eeeb3bc306e94ea08f5464f0
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2017
ms.locfileid: "26686625"
---
# <a name="configure-pipeline-tracking-in-biztalk-server"></a>パイプラインが BizTalk Server での追跡を構成します。
BizTalk Server 管理コンソールを使用すると、パイプラインの追跡を構成できます。 追跡は、トラブルシューティングと監査のために構成できます。 メッセージ プロパティ、ポート イベント、およびメッセージ イベントを表示できます。 メッセージのメッセージ イベントおよびポート イベントも追跡できます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に含まれている既定のパイプラインの 1 つ、または BizTalk アプリケーションに展開されたカスタム パイプラインの追跡を構成できます。 構成する追跡の設定は、パイプラインのすべてのインスタンスに適用されます。  
  
> [!IMPORTANT]
>  パイプラインの追跡を構成できますが、このデータは、パイプラインを使用するすべてのポートに対してグローバルに収集されるため大量のデータが生成されます。 代わりに、ことをお勧め、送信の追跡を構成し、受信ポート、」の説明に従って[送信ポートの追跡を構成する](../core/how-to-configure-tracking-for-a-send-port.md)と[受信ポートの追跡を構成する](../core/how-to-configure-tracking-for-a-receive-port.md)です。  
  
 メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>Prerequisites  
BizTalk Server 管理者グループのメンバーであるアカウントでサインインします。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="enable-pipeline-tracking"></a>パイプラインの追跡を有効にします。
  
1.  **BizTalk Server 管理コンソール**パイプラインが含まれている BizTalk グループを展開します。 
  
2.  次のいずれかの操作を行います。  
  
    -   既定値のいずれかの BizTalk パイプラインの追跡を構成するのには、展開\<すべての成果物\>です。  
  
    -   BizTalk アプリケーションに展開されたカスタム パイプラインの追跡を構成する場合は、パイプラインが含まれているアプリケーションを展開します。  
  
3.  選択、**パイプライン**フォルダーは、パイプラインを右クリックし、**追跡**です。  
  
    > [!NOTE]
    >  複数のパイプラインを一度に、Shift キーを押しながら選択を構成するのには、各パイプラインの追跡を構成するにはパイプラインの 1 つを右クリックし、**追跡**です。  
  
4.  詳細を使用しを選択し、追跡オプションを構成する**OK**して変更を保存します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**イベントの追跡-ポートの開始し、終了イベント**|インスタンスの開始時し、終了時にのみを追跡します。 [詳細] には、項目名、アセンブリ、および他のメタデータが含まれます。|  
    |**イベントの追跡-メッセージの送信および受信イベント**|追跡メッセージの送信およびイベントを受信します。 場合にのみ利用できます**ポートの開始と終了イベント**が選択されています。|  
    |**メッセージ本文の追跡のパイプライン処理前に、のメッセージ**|保存し、Url などのメタデータを保持し、プロパティを昇格するパイプラインで受信メッセージの本文を追跡します。 パイプラインが受信パイプラインの場合、このメッセージ本文は、トランスポート コンポーネントからパイプラインに送信される時点の未処理のメッセージです。 アプリケーションによっては、メッセージは暗号化、署名、またはエンコードされていることがあります。 BizTalk マップを使用するときに、これが受信パイプラインである場合は、追跡は受信マップが処理された後で行われます。<br /><br /> 場合にのみ利用できます**メッセージの送信および受信イベント**が選択されています。|  
    |**メッセージ本文の追跡のパイプライン処理後のメッセージ**|保存し、Url などのメタデータを保持し、昇格させたプロパティがパイプラインによって送信されたメッセージ本文を追跡します。 パイプラインが受信パイプラインの場合、このメッセージ本文は、メッセージ ボックス データベースに送信される時点の処理済みのメッセージです。アプリケーションによっては XML 形式である場合があります。 BizTalk マップを使用するときに、これが送信パイプラインである場合は、追跡は送信マップが処理される前に行われます。<br /><br /> 場合にのみ利用できます**メッセージの送信および受信イベント**が選択されています。|  
  
## <a name="see-also"></a>参照  
 [パイプラインの管理](../core/managing-pipelines.md)
