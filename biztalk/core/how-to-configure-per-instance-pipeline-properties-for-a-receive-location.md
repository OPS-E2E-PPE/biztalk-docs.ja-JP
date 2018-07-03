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
ms.openlocfilehash: 27c591e7ea30dd97b116f89c3d50d03ea48392b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982419"
---
# <a name="how-to-configure-per-instance-pipeline-properties-for-a-receive-location"></a>受信場所のインスタンスごとにパイプライン プロパティを構成する方法
このトピックでは、BizTalk グループにパイプラインを展開した後、BizTalk Server 管理コンソールを使用して受信場所のパイプライン プロパティを構成する方法について説明します。 受信場所のパイプライン プロパティを変更した場合、その受信場所についてのみ、既定のパイプライン プロパティが上書きされます。したがって、BizTalk グループに含まれる各受信場所について、それぞれ異なるパイプライン プロパティを構成することも可能です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
> [!NOTE]
>  インスタンスごとにパイプライン プロパティを使用して、値を設定する場合、 **DocumentSpecNames**同じプロジェクトでパイプラインを指定されたドキュメント スキーマとパイプラインの XML 逆アセンブラー コンポーネントでプロパティを定義する必要があります。  
  
### <a name="to-configure-per-instance-pipeline-properties-for-a-receive-location"></a>受信場所のインスタンスごとにパイプライン プロパティを構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**、パイプライン プロパティを構成する受信場所が含まれる BizTalk グループ**アプリケーション**、し、受信場所を含むアプリケーションを展開します。  
  
3. をクリックして、**受信場所**フォルダーは、受信場所を右クリックし、順にクリックします**プロパティ**します。  
  
4. 右側にある省略記号 (...) をクリックして、**受信パイプライン**ボックス。  
  
5. をクリックし、プロパティを構成する**OK**します。 詳細については、次のようにクリックします。**ヘルプ**[プロパティ] ページ。  
  
   > [!IMPORTANT]
   >  パイプライン プロパティの情報は正しく入力してください。 数値を入力すべきところで文字列を入力するなど、無効な値を入力するとエラーが発生します。  
  
6. この場合、要求-応答受信場所の右側にある省略記号 (...) をクリックして、**送信パイプライン**ボックス。  
  
7. をクリックし、プロパティを構成する**OK** 2 回クリックします。 詳細については、次のようにクリックします。**ヘルプ**[プロパティ] ページ。  
  
## <a name="see-also"></a>参照  
 [パイプラインの管理](../core/managing-pipelines.md)   
 [作成と送信ポートの構成](../core/creating-and-configuring-send-ports.md)   
 [受信場所の管理](../core/managing-receive-locations.md)