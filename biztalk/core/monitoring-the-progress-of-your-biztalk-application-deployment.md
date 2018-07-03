---
title: BizTalk アプリケーション展開の進行状況の監視 |Microsoft Docs
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
ms.openlocfilehash: 07beea810ff64c807685b8170009d5204ede1af7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001155"
---
# <a name="monitoring-the-progress-of-your-biztalk-application-deployment"></a>BizTalk アプリケーション展開の進行状況の監視
BizTalk アプリケーションの展開の進行状況は、2 つの方法で監視できます。  
  
- **BizTalk インストール ログ**: BizTalk Server が生成するインストール ログを参照してください。 インストール ログにある %SystemDrive%\Documents and Settings\\<*現在のユーザー*\>\Application Data\Microsoft\BizTalk Server\Deployment します。  
  
- **ローカル イベント ログ**: ローカル イベント ログで、インストールの進行状況を追跡することができます。 このため、カスタムのインストール動作をサーバー単位で追跡できます。  
  
- **Windows インストーラー ログ**: Microsoft Windows インストーラーには、カスタム アクションのアクション ログに記録する、ローカル コンピューター上のログ ファイルが作成されます。 このログ ファイルは、msiexec コマンドの /log オプションで指定できます。 詳細については、Windows インストーラーのドキュメントを参照してください。  
  
> [!IMPORTANT]
>  プロパティ スキーマの展開または展開解除は機密データの公開につながる可能性があり、追跡時に機密情報が公開されてしまう可能性もあります。 プロパティ スキーマが含まれているアセンブリを展開または展開解除すると、必ずイベント ビューアーによってイベントが Windows アプリケーション イベント ログに記録されます。 イベント ログに記録されているメッセージを調べて、すべてのアセンブリ展開アクティビティが機密データに関するポリシーに従っていることを確認する必要があります。 (展開に関してイベント ログに生成されるメッセージ:"user"{1}「アセンブリの展開」{0}「プロパティのスキーマを格納します」。 展開解除は、イベント ログに生成されたメッセージ:"user"{1}「アセンブリの展開を解除」{0}「プロパティのスキーマを格納します」)。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの展開](../core/deploying-biztalk-applications.md)