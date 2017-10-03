---
title: "エラー - スキーマの依存関係が有効ではありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.schemaDependencyNotValid
ms.assetid: 431278f0-6cd1-4b3f-8d87-16af4991d354
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36326608f191b520c41cb42890aec029c432fd30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---schema-dependency-not-valid"></a><span data-ttu-id="d2c81-102">エラー - スキーマの依存関係が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d2c81-102">Error - Schema Dependency Not Valid</span></span>
<span data-ttu-id="d2c81-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="d2c81-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d2c81-104">BEC2009</span><span class="sxs-lookup"><span data-stu-id="d2c81-104">BEC2009</span></span>  
  
 <span data-ttu-id="d2c81-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="d2c81-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d2c81-106">すべての依存スキーマ (現在のスキーマにインポート、包含、再定義された依存スキーマなど) は、この BizTalk プロジェクトに追加するか、このプロジェクトによって参照されるアセンブリ内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2c81-106">All dependent schemas, such as those that are imported, included, or redefined in the current schema, must be added to this BizTalk project or exist in an assembly referenced by this project.</span></span> <span data-ttu-id="d2c81-107">偶数スキーマ**インポート**、**を含める**、および**を再定義**リモート Web サイト上で指定するディレクティブは、この BizTalk プロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2c81-107">Even schema **import**, **include**, and **redefine** directives that specify schemas on a remote Web site must be added to this BizTalk project.</span></span>  
  
 <span data-ttu-id="d2c81-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="d2c81-108">**User Action**</span></span>  
  
 <span data-ttu-id="d2c81-109">使用して、**既存項目の追加**コマンドを**ファイル**メニューと BizTalk プロジェクトにこのスキーマが依存しているすべてのスキーマを追加する Microsoft® BizTalk® Server プロジェクトのショートカット メニュー。</span><span class="sxs-lookup"><span data-stu-id="d2c81-109">Use the **Add Existing Item** command on the **File** menu and the shortcut menu for the Microsoft® BizTalk® Server project to add all schemas upon which this schema depends to the BizTalk project.</span></span> <span data-ttu-id="d2c81-110">BizTalk プロジェクトにスキーマを追加する前に、スキーマを Web サイトからローカル ハード ディスクにダウンロードする必要が生じる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d2c81-110">You may need to download such schemas from a Web site to your local hard disk before adding them to the BizTalk project.</span></span>