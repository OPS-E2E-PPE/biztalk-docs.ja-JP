---
title: BizTalk Server のバージョンがあるでしょうか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb651202-f682-4e5f-8a79-221877af20a7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 974999da3d74075fa218e078d1a757a83dbd325e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395148"
---
# <a name="what-version-of-biztalk-server-do-i-have"></a>BizTalk Server のバージョンがあるでしょうか。
さまざまなバージョンとのさまざまなエディションを実行して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 このトピックでは、確認する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールについては、バージョン番号、エディション、およびインストール パスを含むです。  

## <a name="use-the-registry"></a>レジストリを使用します。

1. 選択**開始**、型`regedt32`、し、開きます。  

2. 展開**HKEY_LOCAL_MACHINE**、展開**ソフトウェア**、展開**Microsoft**、展開**BizTalk Server**、し、 **3.0**します。  

3. 右側のウィンドウには、インストール情報が表示されます。 など。  


   |      サブ キー       |                                                                                                         説明                                                                                                          |
   |--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  **InstallPath**   |                                             インストールしたインストール パスを一覧表示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。                                              |
   | **ProductEdition** |                                                        エディションの一覧を含みます。<br /><br /> -開発者<br />ブランチ<br />標準<br />-エンタープライズ                                                         |
   | **ProductVersion** | 基本の製品バージョンを一覧表示します。 サービス パックおよび累積更新プログラムを含め、特定の製品バージョンを参照してください。[のバージョンの BizTalk](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx)します。 |

## <a name="use-the-control-panel"></a>コントロール パネルを使用します。

1.  選択**開始**、型`Programs and Features`、し、開きます。  

2. 一覧で、次のように選択します。 **Microsoft BizTalk Server**します。 バージョンおよびエディションの一覧が表示されます。

参照してください[のバージョンの BizTalk](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx)します。

## <a name="see-also"></a>参照  
 [開始するには](../core/getting-started-with-biztalk-server.md)