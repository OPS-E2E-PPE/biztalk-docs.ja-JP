---
title: エラー - スキーマの依存関係が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.schemaDependencyNotValid
ms.assetid: 431278f0-6cd1-4b3f-8d87-16af4991d354
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcee29e7074ca012c11aea738c5fa44c6e702352
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346958"
---
# <a name="error---schema-dependency-not-valid"></a><span data-ttu-id="d0d96-102">エラー - スキーマの依存関係が無効です。</span><span class="sxs-lookup"><span data-stu-id="d0d96-102">Error - Schema Dependency Not Valid</span></span>
<span data-ttu-id="d0d96-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="d0d96-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d0d96-104">BEC2009</span><span class="sxs-lookup"><span data-stu-id="d0d96-104">BEC2009</span></span>  
  
 <span data-ttu-id="d0d96-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="d0d96-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d0d96-106">含まれる、現在のスキーマで再定義または BizTalk プロジェクトに追加する必要があります。 またはこのプロジェクトで参照されるアセンブリ内に存在にインポートされているものなど、すべての依存スキーマ。</span><span class="sxs-lookup"><span data-stu-id="d0d96-106">All dependent schemas, such as those that are imported, included, or redefined in the current schema, must be added to this BizTalk project or exist in an assembly referenced by this project.</span></span> <span data-ttu-id="d0d96-107">スキーマ**インポート**、**含める**、および**再定義**リモート Web サイト上で指定するディレクティブは、この BizTalk プロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0d96-107">Even schema **import**, **include**, and **redefine** directives that specify schemas on a remote Web site must be added to this BizTalk project.</span></span>  
  
 <span data-ttu-id="d0d96-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="d0d96-108">**User Action**</span></span>  
  
 <span data-ttu-id="d0d96-109">使用して、**既存項目の追加**コマンドを**ファイル**メニューと BizTalk プロジェクトにこのスキーマが依存しているすべてのスキーマを追加する Microsoft® BizTalk® Server プロジェクトのショートカット メニュー。</span><span class="sxs-lookup"><span data-stu-id="d0d96-109">Use the **Add Existing Item** command on the **File** menu and the shortcut menu for the Microsoft® BizTalk® Server project to add all schemas upon which this schema depends to the BizTalk project.</span></span> <span data-ttu-id="d0d96-110">BizTalk プロジェクトに追加する前に、ローカル ハード_ディスクに Web サイトからこのようなスキーマをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0d96-110">You may need to download such schemas from a Web site to your local hard disk before adding them to the BizTalk project.</span></span>