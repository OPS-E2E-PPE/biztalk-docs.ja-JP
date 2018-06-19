---
title: インスタンスごとのパイプライン プロパティを構成する方法、受信場所 |Microsoft ドキュメント
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
ms.openlocfilehash: 0e14483c5d17d968fc79126c65506720b501b6da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248842"
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-receive-location"></a>受信場所のインスタンスごとにパイプライン プロパティを構成する方法
このトピックでは、BizTalk グループにパイプラインを展開した後、BizTalk Server 管理コンソールを使用して受信場所のパイプライン プロパティを構成する方法について説明します。 受信場所のパイプライン プロパティを変更した場合、その受信場所についてのみ、既定のパイプライン プロパティが上書きされます。したがって、BizTalk グループに含まれる各受信場所について、それぞれ異なるパイプライン プロパティを構成することも可能です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
> [!NOTE]
>  インスタンスごとにパイプライン プロパティを使用して値を設定する場合、 **DocumentSpecNames**同じプロジェクトでは、XML 逆アセンブラー コンポーネントで、パイプライン、指定されたドキュメント スキーマとパイプラインのプロパティを定義する必要があります。  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-receive-location"></a>受信場所のインスタンスごとにパイプライン プロパティを構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、パイプライン プロパティを構成、展開する対象の受信場所を含む BizTalk グループを展開して**アプリケーション**、し、受信場所を含むアプリケーションを展開します。  
  
3.  クリックして、**受信場所**フォルダーは、受信場所を右クリックし、をクリックして**プロパティ**です。  
  
4.  右側にある省略記号 (...) をクリックして、**受信パイプライン**ボックス。  
  
5.  プロパティを構成しますし、をクリックして**OK**です。 詳細についてをクリックして**ヘルプ**[プロパティ] ページ。  
  
    > [!IMPORTANT]
    >  パイプライン プロパティの情報は正しく入力してください。 数値を入力すべきところで文字列を入力するなど、無効な値を入力するとエラーが発生します。  
  
6.  場合は、要求-応答の受信場所の右側にある省略記号 (...) をクリックして、**送信パイプライン**ボックス。  
  
7.  プロパティを構成しますし、をクリックして**OK** 2 回クリックします。 詳細についてをクリックして**ヘルプ**[プロパティ] ページ。  
  
## <a name="see-also"></a>参照  
 [パイプラインの管理](../core/managing-pipelines.md)   
 [作成して、送信ポートの構成](../core/creating-and-configuring-send-ports.md)   
 [受信場所の管理](../core/managing-receive-locations.md)