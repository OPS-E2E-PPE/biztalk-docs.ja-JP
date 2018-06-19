---
title: BizTalk アプリケーションの展開の進行状況の監視 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring, deploying
- applications, monitoring
- deploying [applications], monitoring
- monitoring, applications
ms.assetid: a69a8288-0203-440f-9805-52786525e193
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a91910fd1955858260466d987bede1647f0be90c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972896"
---
# <a name="monitoring-the-progress-of-your-biztalk-application-deployment"></a>BizTalk アプリケーション展開の進行状況の監視
BizTalk アプリケーションの展開の進行状況は、2 つの方法で監視できます。  
  
-   **BizTalk インストール ログ**: インストールを参照してくださいをログに記録[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が生成されます。 インストール ログに %SystemDrive%\Documents and Settings\\<*現在のユーザー*\>\Application Data\Microsoft\\[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]\Deployment です。  
  
-   **ローカル イベント ログ**: ローカル イベント ログで、インストールの進行状況を追跡することができます。 このため、カスタムのインストール動作をサーバー単位で追跡できます。  
  
-   **Windows インストーラーのログ**: Microsoft Windows インストーラーが、カスタム アクションのアクション ログに記録するローカル コンピューター上のログ ファイルを作成します。 このログ ファイルは、msiexec コマンドの /log オプションで指定できます。 詳細については、Windows インストーラーのドキュメントを参照してください。  
  
> [!IMPORTANT]
>  プロパティ スキーマの展開または展開解除は機密データの公開につながる可能性があり、追跡時に機密情報が公開されてしまう可能性もあります。 プロパティ スキーマが含まれているアセンブリを展開または展開解除すると、必ずイベント ビューアーによってイベントが Windows アプリケーション イベント ログに記録されます。 イベント ログに記録されているメッセージを調べて、すべてのアセンブリ展開アクティビティが機密データに関するポリシーに従っていることを確認する必要があります。 (展開に関してイベント ログに生成されるメッセージ:「ユーザー「{1}」には、"{0}"プロパティのスキーマを含んでいるアセンブリが展開されている」です。 展開解除に関してイベント ログに生成されるメッセージ:「「{1}」ユーザーは、"{0}"プロパティのスキーマを含んでいるアセンブリを展開解除」です)。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの展開](../core/deploying-biztalk-applications.md)