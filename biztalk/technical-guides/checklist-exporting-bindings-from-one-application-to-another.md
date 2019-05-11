---
title: チェックリスト:別のアプリケーションへのバインドのエクスポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 152924e6-da64-4db9-a852-bdb4e79687fb
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7da1e88eb3745c60630827732ac92d167e4520b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401841"
---
# <a name="checklist-exporting-bindings-from-one-application-to-another"></a>チェックリスト:別のアプリケーションへのバインドのエクスポート
このトピックでは、開発または実稼働環境で別のアプリケーションに 1 つのアプリケーションのバインドを転送するための手順について説明します。 このプロセスは、.msi ファイルを使用してアプリケーションをデプロイするプロセスに似ています。 ただし、.msi ファイルを使用してアプリケーションを展開する場合でも、プロセス、アプリケーションが自動的に作成します。 別のアプリケーションへのバインドを転送するときにその一方で、コピー先のアプリケーションが存在する必要があります既に。  
  
|手順|リファレンス|  
|-----------|---------------|  
|エクスポート操作を実行する適切なアクセス許可があることを確認します。|[アプリケーションを管理するためのアクセス許可](../technical-guides/permissions-for-managing-an-application.md)|  
|アプリケーションのバインドをインポートする先のアプリケーションを作成します。|-   [アプリケーションを作成します。](../technical-guides/creating-an-application.md)<br />-「BizTalk アプリケーションを作成する」のセクションの[アプリケーションを展開するためのベスト プラクティス](../technical-guides/best-practices-for-deploying-an-application.md)|  
|バインド ファイルへの送信元アプリケーションのバインドをエクスポートします。|-   [バインド ファイルにバインドをエクスポートする方法](../technical-guides/how-to-export-bindings-to-a-binding-file.md)<br />-「BizTalk アプリケーションをエクスポートする」のセクションの[アプリケーションを展開するためのベスト プラクティス](../technical-guides/best-practices-for-deploying-an-application.md)<br />-「BizTalk アプリケーションをエクスポートする」のセクションの[アプリケーションの展開に関する既知の問題](../technical-guides/known-issues-with-deploying-an-application.md)します。|  
|コピー先のアプリケーションには、バインド ファイル内のバインドをインポートします。|-   [バインド ファイルからバインドをインポートする方法](../technical-guides/how-to-import-bindings-from-a-binding-file.md)<br />-「BizTalk アプリケーションをインポートする」のセクションの[アプリケーションを展開するためのベスト プラクティス](../technical-guides/best-practices-for-deploying-an-application.md)<br />-「BizTalk アプリケーションをインポートする」のセクションの[アプリケーションの展開に関する既知の問題](../technical-guides/known-issues-with-deploying-an-application.md)します。|