---
title: ファイル アダプタ プロパティ スキーマおよびプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [File adapters], properties
- schemas, File adapters
- File adapters, schemas
- Password property [File adapters]
- ReceivedFileName property [File adapters]
- configuring [File adapters], schemas
- CopyMode property [File adapters]
- AllowCacheOnWrite property [File adapters]
- FileCreationTime property [File adapters]
- UserName property, File adapters
- File adapters, properties
- UserName property
ms.assetid: c5ae5339-67bf-4fde-a721-5b1aa3b9caca
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5671243de2ec3d3f97c8edf80d0de94a547301fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388049"
---
# <a name="file-adapter-property-schema-and-properties"></a><span data-ttu-id="ab20f-102">ファイル アダプター プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="ab20f-102">File adapter property schema and properties</span></span>
<span data-ttu-id="ab20f-103">次の表には、ファイル アダプター プロパティ スキーマのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab20f-103">The following table contains the properties in the File adapter property schema.</span></span>  
  
 <span data-ttu-id="ab20f-104">**名前空間:** http://schemas.microsoft.com/BizTalk/2003/file-properties</span><span class="sxs-lookup"><span data-stu-id="ab20f-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/file-properties</span></span>  
  
|<span data-ttu-id="ab20f-105">名前</span><span class="sxs-lookup"><span data-stu-id="ab20f-105">Name</span></span>|<span data-ttu-id="ab20f-106">型</span><span class="sxs-lookup"><span data-stu-id="ab20f-106">Type</span></span>|<span data-ttu-id="ab20f-107">説明</span><span class="sxs-lookup"><span data-stu-id="ab20f-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="ab20f-108">**CopyMode**</span><span class="sxs-lookup"><span data-stu-id="ab20f-108">**CopyMode**</span></span>|<span data-ttu-id="ab20f-109">xs:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ab20f-109">xs:unsignedInt</span></span>|<span data-ttu-id="ab20f-110">ファイルにメッセージを書き込むときに使用するコピー モードを定義します。</span><span class="sxs-lookup"><span data-stu-id="ab20f-110">Defines the copy mode to use when writing a message to a file.</span></span> <span data-ttu-id="ab20f-111">有効な値は、</span><span class="sxs-lookup"><span data-stu-id="ab20f-111">Valid values are:</span></span><br /><br /> <span data-ttu-id="ab20f-112">**(0) を追加します。**</span><span class="sxs-lookup"><span data-stu-id="ab20f-112">**Append (0).**</span></span> <span data-ttu-id="ab20f-113">ファイルが存在する場合は、ファイル送信ハンドラがファイルを開き、ファイルの末尾にメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="ab20f-113">The File send handler opens a file if it exists and appends a message to the end of the file.</span></span> <span data-ttu-id="ab20f-114">ファイルが存在しない場合は、ファイル送信ハンドラが新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab20f-114">If the file does not exist, the File send handler creates a new file.</span></span><br /><br /> <span data-ttu-id="ab20f-115">**新しい (1) を作成します。**</span><span class="sxs-lookup"><span data-stu-id="ab20f-115">**Create new (1).**</span></span> <span data-ttu-id="ab20f-116">ファイルが存在しない場合は、ファイル送信ハンドラが新しいファイルを作成し、そのファイルにメッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="ab20f-116">If a file does not exist, the File send handler creates a new file and writes to it.</span></span> <span data-ttu-id="ab20f-117">ファイルが存在する場合は、ファイル送信ハンドラがエラーを報告し、送信ポートの通常のアダプタ再試行ロジックに従ってメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="ab20f-117">If the file already exists, the File send handler reports an error and then follows common adapter retry logic for send ports.</span></span> <span data-ttu-id="ab20f-118">これはファイル送信ハンドラの既定のコピー モードです。</span><span class="sxs-lookup"><span data-stu-id="ab20f-118">This is a default copy mode for the File send handler.</span></span><br /><br /> <span data-ttu-id="ab20f-119">**(2) を上書きします。**</span><span class="sxs-lookup"><span data-stu-id="ab20f-119">**Overwrite (2).**</span></span> <span data-ttu-id="ab20f-120">ファイルが存在する場合は、ファイル送信ハンドラがファイルを開き、ファイルの内容を上書きします。</span><span class="sxs-lookup"><span data-stu-id="ab20f-120">The File send handler opens a file if it exists and overwrites its content.</span></span> <span data-ttu-id="ab20f-121">ファイルが存在しない場合は、ファイル送信ハンドラが新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab20f-121">If the file does not exist, the File send handler creates a new file.</span></span>|  
|<span data-ttu-id="ab20f-122">**AllowCacheOnWrite**</span><span class="sxs-lookup"><span data-stu-id="ab20f-122">**AllowCacheOnWrite**</span></span>|<span data-ttu-id="ab20f-123">xs:Boolean</span><span class="sxs-lookup"><span data-stu-id="ab20f-123">xs:Boolean</span></span>|<span data-ttu-id="ab20f-124">ファイル システム キャッシュをファイルにメッセージを書き込むときに、ファイル アダプタが使用するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="ab20f-124">Defines whether the File adapter uses file system caching when writing messages to a file.</span></span>|  
|<span data-ttu-id="ab20f-125">**ReceivedFileName**</span><span class="sxs-lookup"><span data-stu-id="ab20f-125">**ReceivedFileName**</span></span>|<span data-ttu-id="ab20f-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab20f-126">xs:string</span></span>|<span data-ttu-id="ab20f-127">ファイル アダプターがメッセージを読み取るファイルの完全名を定義します。</span><span class="sxs-lookup"><span data-stu-id="ab20f-127">Defines the full name of the file from which the File adapter reads the message.</span></span>|  
|<span data-ttu-id="ab20f-128">**FileCreationTime**</span><span class="sxs-lookup"><span data-stu-id="ab20f-128">**FileCreationTime**</span></span>|<span data-ttu-id="ab20f-129">xs:datetime</span><span class="sxs-lookup"><span data-stu-id="ab20f-129">xs:datetime</span></span>|<span data-ttu-id="ab20f-130">ファイルが書き込まれた時刻を定義ファイルによって監視されているフォルダーには、受信アダプター。</span><span class="sxs-lookup"><span data-stu-id="ab20f-130">Defines the time that the file was written to the folder that is monitored by the File receive adapter.</span></span>|  
|<span data-ttu-id="ab20f-131">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="ab20f-131">**Username**</span></span>|<span data-ttu-id="ab20f-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab20f-132">xs:string</span></span>|<span data-ttu-id="ab20f-133">代替資格情報を指定するときにネットワーク共有にアクセスするために使用するアカウントのユーザー名を定義します。</span><span class="sxs-lookup"><span data-stu-id="ab20f-133">Defines the user name for the account used when specifying alternative credentials to access a network share.</span></span>|  
|<span data-ttu-id="ab20f-134">**Password**</span><span class="sxs-lookup"><span data-stu-id="ab20f-134">**Password**</span></span>|<span data-ttu-id="ab20f-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab20f-135">xs:string</span></span>|<span data-ttu-id="ab20f-136">代替資格情報を指定するときにネットワーク共有にアクセスするために使用するアカウントのパスワードを定義します。</span><span class="sxs-lookup"><span data-stu-id="ab20f-136">Defines the password for the account used when specifying alternative credentials to access a network share.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab20f-137">参照</span><span class="sxs-lookup"><span data-stu-id="ab20f-137">See Also</span></span>  
 [<span data-ttu-id="ab20f-138">ファイル アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="ab20f-138">Configuring the File Adapter</span></span>](../core/configure-the-file-adapter.md)