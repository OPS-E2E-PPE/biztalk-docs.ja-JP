---
title: ロール リンクの管理 |Microsoft Docs
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
ms.openlocfilehash: e31ec8af7f8c5dd785b471654e9a9cfd7446bbf3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998947"
---
# <a name="manage-role-links"></a>ロール リンクを管理します。

## <a name="overview"></a>概要
このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk アプリケーションのロール リンクを管理する方法について説明します。 ロール リンクとは、企業間取引にかかわるパーティ間の関係を定義し、両方向の連携に使用されるメッセージとポートの種類を指定するものです。 ロール リンクの背景については、[オーケストレーションでロール リンクを使用して](../core/using-role-links-in-orchestrations.md)を参照してください。  

## <a name="added-to-application"></a>アプリケーションに追加  
 ロール リンクは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk アセンブリとしてビルドおよびコンパイルされます。 ロール リンクを単独でアプリケーションに追加することはできません。ロール リンクは次のようにしてアプリケーションに追加されます。  
  
- 」の説明に従って、アプリケーションにロール リンクを含む BizTalk アセンブリを追加するときに[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)します。  
  
- 」の説明に従って、ロール リンクを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートする[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。  
  
- 開発者が展開したときに、アプリケーションからのロール リンクを含むアセンブリ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。  

## <a name="deploy-to-production"></a>運用環境にデプロイします。  
 BizTalk アプリケーションの開発者は、ロール リンクを作成することにより、企業間取引にかかわる複数のパーティ間 (企業とその業者など) の通信を実装します。 開発者が指定するのはロールだけでよく、取引にかかわるパーティを指定する必要はありません。 ロール リンクを含むアプリケーションを実稼働環境に展開し、パーティ間の実際の通信を有効にするには、このセクションに書かれた手順に従い、次の構成作業を行う必要があります。  
  
- ロール リンクに定義された各ロールにパーティを割り当てる (開発プロセス中に行っていない場合)。 これを、ロールに対してパーティを "参加させる" と言います。 後で割り当てが不要になった場合は、そのパーティの参加をロールから解除することもできます。  
  
- ロール リンクに定義された各パーティの論理ポートを、アプリケーションがホストされる BizTalk ホスト インスタンスの物理的ポートにバインドする。  
  
  ロール リンクの開発に関する詳細については、[オーケストレーションでロール リンクを使用して](../core/using-role-links-in-orchestrations.md)を参照してください。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用方法の詳細については、、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。  
  
## <a name="next-step"></a>次の手順
  
-   [参加またはロールに対してパーティを参加解除する方法](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)