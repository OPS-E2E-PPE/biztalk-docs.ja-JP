---
title: ロール リンクの管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8860e11-3d2c-450f-a7d2-cc116478999c
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07f85bfe0d16b3963b0ba18585220f508f679346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262634"
---
# <a name="manage-role-links"></a>ロール リンクを管理します。

## <a name="overview"></a>概要
このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk アプリケーションのロール リンクを管理する方法について説明します。 ロール リンクとは、企業間取引にかかわるパーティ間の関係を定義し、両方向の連携に使用されるメッセージとポートの種類を指定するものです。 ロール リンクの背景情報については、次を参照してください。[オーケストレーションでロール リンクを使用して](../core/using-role-links-in-orchestrations.md)です。  

## <a name="added-to-application"></a>アプリケーションに追加  
 ロール リンクは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk アセンブリとしてビルドおよびコンパイルされます。 ロール リンクを単独でアプリケーションに追加することはできません。ロール リンクは次のようにしてアプリケーションに追加されます。  
  
-   」の説明に従って、アプリケーションにロール リンクを含む BizTalk アセンブリを追加すると[BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)です。  
  
-   」の説明に従って、ロール リンクを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートしたとき[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。  
  
-   開発者が展開したときにアプリケーションから、ロール リンクを含むアセンブリ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。  

## <a name="deploy-to-production"></a>実稼働環境に展開します。  
 BizTalk アプリケーションの開発者は、ロール リンクを作成することにより、企業間取引にかかわる複数のパーティ間 (企業とその業者など) の通信を実装します。 開発者が指定するのはロールだけでよく、取引にかかわるパーティを指定する必要はありません。 ロール リンクを含むアプリケーションを実稼働環境に展開し、パーティ間の実際の通信を有効にするには、このセクションに書かれた手順に従い、次の構成作業を行う必要があります。  
  
-   ロール リンクに定義された各ロールにパーティを割り当てる (開発プロセス中に行っていない場合)。 これを、ロールに対してパーティを "参加させる" と言います。 後で割り当てが不要になった場合は、そのパーティの参加をロールから解除することもできます。  
  
-   ロール リンクに定義された各パーティの論理ポートを、アプリケーションがホストされる BizTalk ホスト インスタンスの物理的ポートにバインドする。  
  
 ロール リンクの開発に関する詳細については、次を参照してください。[オーケストレーションでロール リンクを使用して](../core/using-role-links-in-orchestrations.md)です。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
## <a name="next-step"></a>次の手順
  
-   [参加させる、またはロールに対してパーティを参加解除する方法](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)