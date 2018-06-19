---
title: 送信ポートのインスタンスごとにパイプライン プロパティを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: cfb9927dca890a7f84baf372c4fa250a8ced17c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249266"
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-send-port"></a>送信ポートのインスタンスごとにパイプライン プロパティを構成する方法
ここでは、BizTalk グループにパイプラインを展開した後、BizTalk Server 管理コンソールを使用して送信ポートのパイプライン プロパティを構成する方法について説明します。 送信ポートのパイプライン プロパティを変更した場合、その送信ポートについてのみ、既定のパイプライン プロパティが上書きされます。したがって、BizTalk グループに含まれる各送信ポートについて、それぞれ異なるパイプライン プロパティを構成することも可能です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
> [!NOTE]
>  インスタンスごとにパイプライン プロパティを使用して値を設定する場合、 **DocumentSpecNames**同じプロジェクトでは、XML 逆アセンブラー コンポーネントで、パイプライン、指定されたドキュメント スキーマとパイプラインのプロパティを定義する必要があります。  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-send-port"></a>送信ポートのインスタンスごとにパイプライン プロパティを構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、パイプライン プロパティを構成、展開する送信ポートを含む BizTalk グループを展開して**アプリケーション**、し、送信ポートを含むアプリケーションを展開します。  
  
3.  クリックして、**送信ポート**フォルダーは、送信ポートを右クリックし、をクリックして**プロパティ**です。  
  
4.  省略記号ボタン (**.**) の右側にあるボタン、**送信パイプライン**ボックス。  
  
5.  プロパティを構成しますし、をクリックして**OK**です。 をクリックして**ヘルプ**詳細については、プロパティ ページにします。  
  
    > [!IMPORTANT]
    >  パイプライン プロパティの情報は正しく入力してください。 数値を入力すべきところで文字列を入力するなど、無効な値を入力するとエラーが発生します。  
  
6.  送信請求-応答送信ポートの場合は、省略記号ボタンをクリックして (**.**) の右側にあるボタン、**受信パイプライン**ボックス。  
  
7.  プロパティを構成しますし、をクリックして**OK** 2 回クリックします。 をクリックして**ヘルプ**詳細については、プロパティ ページにします。  
  
## <a name="see-also"></a>参照  
 [パイプラインの管理](../core/managing-pipelines.md)   
 [作成して、送信ポートの構成](../core/creating-and-configuring-send-ports.md)   
 [受信場所の管理](../core/managing-receive-locations.md)