---
title: インスタンスごとのパイプライン プロパティを構成する方法、受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- receive locations, configuring
- managing [pipelines], properties
- managing [pipelines], receive locations
- managing [receive locations], pipelines
- managing [pipelines], configuring
- pipelines, receive locations
- pipelines, configuring
- receive locations, pipelines
- managing [receive locations], configuring
ms.assetid: e1ed3b10-2f39-479b-a3e6-22b4b2872192
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fb31801e832c190ee4c9d00d7dcaa055a4f43fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386208"
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-receive-location"></a>インスタンスごとのパイプライン プロパティを構成する方法、受信場所
このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk グループにパイプラインを展開した後、受信場所のパイプライン プロパティを構成する方法について説明します。 この既定のパイプライン プロパティを上書き変更の受信場所のみ、BizTalk グループ内の受信場所をそれぞれ異なるパイプライン プロパティをする場合は、構成できるようにします。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
> [!NOTE]
>  インスタンスごとにパイプライン プロパティを使用して、値を設定する場合、 **DocumentSpecNames**同じプロジェクトでパイプラインを指定されたドキュメント スキーマとパイプラインの XML 逆アセンブラー コンポーネントでプロパティを定義する必要があります。  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-receive-location"></a>受信場所のインスタンスごとのパイプライン プロパティを構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**、パイプライン プロパティを構成する受信場所が含まれる BizTalk グループ**アプリケーション**、し、受信場所を含むアプリケーションを展開します。  
  
3. をクリックして、**受信場所**フォルダーは、受信場所を右クリックし、順にクリックします**プロパティ**します。  
  
4. 右側にある省略記号 (...) をクリックして、**受信パイプライン**ボックス。  
  
5. をクリックし、プロパティを構成する**OK**します。 詳細については、次のようにクリックします。**ヘルプ**[プロパティ] ページ。  
  
   > [!IMPORTANT]
   >  パイプラインのプロパティの正しい情報を入力することを確認します。 数値ではなく文字列など、無効な値を入力すると、エラーが生成されます。  
  
6. この場合、要求-応答受信場所の右側にある省略記号 (...) をクリックして、**送信パイプライン**ボックス。  
  
7. をクリックし、プロパティを構成する**OK** 2 回クリックします。 詳細については、次のようにクリックします。**ヘルプ**[プロパティ] ページ。  
  
## <a name="see-also"></a>参照  
 [パイプラインの管理](../core/managing-pipelines.md)   
 [作成と送信ポートの構成](../core/creating-and-configuring-send-ports.md)   
 [受信場所の管理](../core/managing-receive-locations.md)