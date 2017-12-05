---
title: "スクリプトを使用してアプリケーションを展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e683c5f-7576-4382-9952-d577cd00186c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bc96c3b591baf81806182b6c3e988a46dd208ba
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="using-scripts-to-deploy-applications"></a>スクリプトを使用してアプリケーションを展開するには
スクリプトを使用して、可能な場合は、BizTalk アプリケーションを展開する必要があります。 スクリプト、展開プロセス中に人的ミスのリスクが軽減されます。 深さの展開手順も文書化する必要があります。 非常に詳細な手順とスクリプトのないものを文書化する必要があります。 これには、外部システムと Microsoft 以外のコンポーネントの展開のすべての変更を文書化が含まれます。  
  
## <a name="using-btstask"></a>BTSTask の使用  
 BTSTask.exe を使用するには、BizTalk アプリケーションにも既存のインポートについての作成をスクリプトに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].msi パッケージです。 場合は、アプリケーションの作成をスクリプトに含めるし、パッケージに自動的に構築できますビルド サーバーで自動プロセスを使用しています。  
  
 BizTalk アプリケーションの展開をスクリプト作成の詳細については、次のトピックを参照してください。  
  
-   [展開して、BizTalk アプリケーションを管理する](http://go.microsoft.com/fwlink/?LinkId=154210)(http://go.microsoft.com/fwlink/?LinkId=154210)  
  
-   [BizTalk Server アプリケーションの展開を理解する](http://go.microsoft.com/fwlink/?LinkId=101599)(http://go.microsoft.com/fwlink/?LinkId=101599)  
  
    > [!NOTE]  
    >  この後者の記事は、BizTalk Server にも適用されます。  
  
## <a name="see-also"></a>参照  
 [チェックリスト: BizTalk Server の構成](../technical-guides/checklist-configuring-biztalk-server.md)