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
ms.openlocfilehash: 2d1d49f0c6f54341c14cb14c38cc0de7fefaa9a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991003"
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-send-port"></a>送信ポートのインスタンスごとにパイプライン プロパティを構成する方法
ここでは、BizTalk グループにパイプラインを展開した後、BizTalk Server 管理コンソールを使用して送信ポートのパイプライン プロパティを構成する方法について説明します。 送信ポートのパイプライン プロパティを変更した場合、その送信ポートについてのみ、既定のパイプライン プロパティが上書きされます。したがって、BizTalk グループに含まれる各送信ポートについて、それぞれ異なるパイプライン プロパティを構成することも可能です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
> [!NOTE]
>  インスタンスごとにパイプライン プロパティを使用して、値を設定する場合、 **DocumentSpecNames**同じプロジェクトでパイプラインを指定されたドキュメント スキーマとパイプラインの XML 逆アセンブラー コンポーネントでプロパティを定義する必要があります。  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-send-port"></a>送信ポートのインスタンスごとにパイプライン プロパティを構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**、パイプライン プロパティを構成する送信ポートが含まれる BizTalk グループ**アプリケーション**、し、送信ポートを含むアプリケーションを展開します。  
  
3. をクリックして、**送信ポート**フォルダー、送信ポートを右クリックしておよびクリックして**プロパティ**。  
  
4. 省略記号をクリックします (**.**) の右側にボタン、**送信パイプライン**ボックス。  
  
5. をクリックし、プロパティを構成する**OK**します。 クリックして**ヘルプ**の詳細については、プロパティ ページ。  
  
   > [!IMPORTANT]
   >  パイプライン プロパティの情報は正しく入力してください。 数値を入力すべきところで文字列を入力するなど、無効な値を入力するとエラーが発生します。  
  
6. 送信請求-応答の送信ポートの場合は、省略記号をクリックします (**.。**) の右側にボタン、**受信パイプライン**ボックス。  
  
7. をクリックし、プロパティを構成する**OK** 2 回クリックします。 クリックして**ヘルプ**の詳細については、プロパティ ページ。  
  
## <a name="see-also"></a>参照  
 [パイプラインの管理](../core/managing-pipelines.md)   
 [作成と送信ポートの構成](../core/creating-and-configuring-send-ports.md)   
 [受信場所の管理](../core/managing-receive-locations.md)