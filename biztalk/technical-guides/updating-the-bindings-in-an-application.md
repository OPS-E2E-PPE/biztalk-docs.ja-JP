---
title: アプリケーションのバインドの更新 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe4ee4d8-67bf-4137-94e2-8274107c8ed6
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d4d30296a2bb81b3685793884010f02eb950828
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="updating-the-bindings-in-an-application"></a>アプリケーションのバインドを更新
アプリケーションのアセンブリを更新すると、多くの場合、そのバインドが上書きされます。また、アセンブリがまったくバインドされず、バインドの再構成を手動で行う必要が生じることもあります。 これを回避するのには、同じバージョンのアセンブリを更新または新しいバージョンでアセンブリを更新するバインド ファイルを使用できます。  
  
## <a name="updating-the-same-version-of-an-assembly"></a>アセンブリの同じバージョンの更新  
 アセンブリに事前バインドされたポートまたは動的ポートがあり、ポート構成を BizTalk Server 管理コンソールで変更した場合、このアセンブリを同じバージョン番号のアセンブリで更新すると、設定は失われます。 更新しようとするアセンブリのバインド ファイルをエクスポートすることができます。 アセンブリを更新した後、アプリケーションにアセンブリをインポートし、以前のバインドを再適用するには、そのバインド ファイルをインポートできます。  
  
## <a name="updating-an-assembly-with-a-newer-version"></a>アセンブリを新しいバージョンと更新  
 アセンブリのバージョンを更新するには、バインド ファイルに 1 つのアセンブリに関連付けられているバインディング、アセンブリの新しいバージョンを反映するように、バインド ファイルを編集し、アプリケーションにアセンブリのバインドのインポートおよびエクスポートします。 バインド ファイルの編集の詳細については、次を参照してください。[バインド ファイルのカスタマイズ](http://go.microsoft.com/fwlink/?LinkID=155000)(ハイパーリンク"http://go.microsoft.com/fwlink/?LinkID=155000" http://go.microsoft.com/fwlink/?LinkID=155000) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。