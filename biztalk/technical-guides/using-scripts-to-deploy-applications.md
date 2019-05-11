---
title: スクリプトを使用してアプリケーションを展開する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e683c5f-7576-4382-9952-d577cd00186c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5e8c4018540562f92d80f8c2529deebedcc9753
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249312"
---
# <a name="using-scripts-to-deploy-applications"></a>スクリプトを使用してアプリケーションを展開するには
スクリプトを使用して、可能であれば、BizTalk アプリケーションをデプロイする必要があります。 展開プロセス中に人的ミスのリスクを軽減するスクリプトします。 展開手順の詳細も文書化する必要があります。 非常に詳細な手順をスクリプトのないものはすべて文書化する必要があります。 これは、Microsoft 以外のコンポーネントの展開を外部システムに変更を文書化が含まれます。  
  
## <a name="using-btstask"></a>BTSTask を使用します。  
 BTSTask.exe を使用するには、BizTalk アプリケーションにも、既存のインポートの作成をスクリプト化する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].msi パッケージ。 アプリケーションの作成をスクリプト化すると、パッケージ作成できる場合に自動的にビルド サーバーで、自動化されたプロセスを使用しています。  
  
 BizTalk アプリケーションの展開をスクリプト作成の詳細については、次のトピックを参照してください。  
  
-   [BizTalk アプリケーション展開、管理](http://go.microsoft.com/fwlink/?LinkId=154210)(http://go.microsoft.com/fwlink/?LinkId=154210)  
  
-   [BizTalk Server アプリケーションの展開について](http://go.microsoft.com/fwlink/?LinkId=101599)(http://go.microsoft.com/fwlink/?LinkId=101599)  
  
    > [!NOTE]  
    >  この後者の記事では、BizTalk Server にも適用されます。  
  
## <a name="see-also"></a>参照  
 [チェックリスト:BizTalk Server の構成](../technical-guides/checklist-configuring-biztalk-server.md)