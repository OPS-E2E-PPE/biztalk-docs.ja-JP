---
title: 送信ポートのインスタンスごとのパイプライン プロパティを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- managing [pipelines], properties
- configuring, send ports
- configuring, pipelines
- managing [pipelines], configuring
- managing [send ports], pipelines
- managing [send ports], configuring
- send ports, pipelines
- pipelines, configuring
ms.assetid: c58faa9e-0dfb-458b-8f1b-d3c91bce0436
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49ab5b83ae12cd6de262e23ed2136f1c9a886d57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341239"
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-send-port"></a>送信ポートのインスタンスごとのパイプライン プロパティを構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk グループにパイプラインを展開した後、送信ポートのパイプライン プロパティを構成する方法について説明します。 既定値を上書き変更パイプラインのみ、この送信ポートのプロパティの場合は、BizTalk グループの送信ポートごとに異なるパイプライン プロパティを構成できるようにします。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
> [!NOTE]
>  インスタンスごとにパイプライン プロパティを使用して、値を設定する場合、 **DocumentSpecNames**同じプロジェクトでパイプラインを指定されたドキュメント スキーマとパイプラインの XML 逆アセンブラー コンポーネントでプロパティを定義する必要があります。  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-send-port"></a>送信ポートのインスタンスごとのパイプライン プロパティを構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**、パイプライン プロパティを構成する送信ポートが含まれる BizTalk グループ**アプリケーション**、し、送信ポートを含むアプリケーションを展開します。  
  
3. をクリックして、**送信ポート**フォルダー、送信ポートを右クリックしておよびクリックして**プロパティ**。  
  
4. 省略記号をクリックします (**.**) の右側にボタン、**送信パイプライン**ボックス。  
  
5. をクリックし、プロパティを構成する**OK**します。 クリックして**ヘルプ**の詳細については、プロパティ ページ。  
  
   > [!IMPORTANT]
   >  パイプラインのプロパティの正しい情報を入力することを確認します。 数値ではなく文字列など、無効な値を入力すると、エラーが生成されます。  
  
6. 送信請求-応答の送信ポートの場合は、省略記号をクリックします (**...**) の右側にボタン、**受信パイプライン**ボックス。  
  
7. をクリックし、プロパティを構成する**OK** 2 回クリックします。 クリックして**ヘルプ**の詳細については、プロパティ ページ。  
  
## <a name="see-also"></a>参照  
 [パイプラインの管理](../core/managing-pipelines.md)   
 [作成と送信ポートの構成](../core/creating-and-configuring-send-ports.md)   
 [受信場所の管理](../core/managing-receive-locations.md)