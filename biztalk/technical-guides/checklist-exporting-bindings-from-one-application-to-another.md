---
title: "チェックリスト: から別のアプリケーションへのバインドのエクスポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 152924e6-da64-4db9-a852-bdb4e79687fb
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df60a6fd1b266403a5c43b5f76bf7594cad4f41a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-exporting-bindings-from-one-application-to-another"></a>チェックリスト: から別のアプリケーションへのバインドのエクスポート
このトピックでは、開発または実稼働環境で別のアプリケーションに 1 つのアプリケーションのバインドの転送に必要な手順について説明します。 このプロセスは、.msi ファイルを使用してアプリケーションの展開プロセスに似ています。 ただし、.msi ファイルを使用してアプリケーションを展開する場合でも、プロセス、アプリケーションが自動的に作成します。 転送する場合、バインドを別の 1 つのアプリケーションから、その一方で、コピー先のアプリケーションが既に存在しています。  
  
|手順|リファレンス|  
|-----------|---------------|  
|エクスポート操作を実行する適切なアクセス許可があることを確認します。|[アプリケーションを管理するためのアクセス許可](../technical-guides/permissions-for-managing-an-application.md)|  
|アプリケーションのバインドをインポートする送信先アプリケーションを作成します。|-   [アプリケーションを作成します。](../technical-guides/creating-an-application.md)<br />-「BizTalk アプリケーションを作成する」のセクションの[アプリケーションを展開するためのベスト プラクティス](../technical-guides/best-practices-for-deploying-an-application.md)|  
|バインド ファイルへの送信元アプリケーションのバインドをエクスポートします。|-   [バインドをバインド ファイルにエクスポートする方法](../technical-guides/how-to-export-bindings-to-a-binding-file.md)<br />-のセクションの「BizTalk アプリケーションをエクスポートする」[アプリケーションを展開するためのベスト プラクティス](../technical-guides/best-practices-for-deploying-an-application.md)<br />-のセクションの「BizTalk アプリケーションをエクスポートする」[に関する既知の問題をアプリケーションを配置する](../technical-guides/known-issues-with-deploying-an-application.md)です。|  
|コピー先のアプリケーションにバインド ファイル内のバインドをインポートします。|-   [バインド ファイルからバインドをインポートする方法](../technical-guides/how-to-import-bindings-from-a-binding-file.md)<br />-のセクションの「BizTalk アプリケーションのインポート」[アプリケーションを展開するためのベスト プラクティス](../technical-guides/best-practices-for-deploying-an-application.md)<br />-のセクションの「BizTalk アプリケーションのインポート」[に関する既知の問題をアプリケーションを配置する](../technical-guides/known-issues-with-deploying-an-application.md)です。|