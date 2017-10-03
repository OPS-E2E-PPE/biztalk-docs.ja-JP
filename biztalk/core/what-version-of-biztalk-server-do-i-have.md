---
title: "ご使用の BizTalk Server のバージョンを確認する方法 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb651202-f682-4e5f-8a79-221877af20a7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce5508a3b7c78e52fe5fcbef40e351dce58f2816
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-version-of-biztalk-server-do-i-have"></a>ご使用の BizTalk Server のバージョンを確認する方法
別のバージョンと異なるエディションを実行して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 このトピックで説明する方法を決定する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールについては、バージョン番号、エディション、およびインストール パスを含むです。  
  
## <a name="use-the-registry"></a>レジストリを使用します。
  
1.  選択**開始**、型`regedt32`、し、開きます。  
  
2.  展開**HKEY_LOCAL_MACHINE**、展開**ソフトウェア**、展開**Microsoft**、展開**BizTalk Server**、し、 **3.0**です。  
  
3.  右側のウィンドウに以下のインストール情報が表示されます。  
  
    |サブキー|Description|  
    |--------------|-----------------|  
    |**インストール パス**|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしたインストール パスがリストされます。|  
    |**ProductEdition**|以下のエディションがリストされます。<br /><br /> -開発者<br />ブランチ<br />標準<br />-エンタープライズ|  
    |**ProductVersion**|基本の製品バージョンがリストされます。 サービス パックおよび累積更新プログラムを含め、特定の製品バージョンを参照してください。[のバージョンの BizTalk](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx)です。|  

## <a name="use-the-control-panel"></a>コントロール パネルを使用します。

1.  選択**開始**、型`Programs and Features`、し、開きます。  

2. 一覧で、次のように選択します。 **Microsoft BizTalk Server**です。 バージョンおよびエディションの一覧が表示されます。

参照してください[のバージョンの BizTalk](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx)です。
  
## <a name="see-also"></a>参照  
 [開始するには](../core/getting-started-with-biztalk-server.md)