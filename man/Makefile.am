libmandir = $(LIB_MAN_DIR)

LIB_MAN_DIR_SUFFIX = $(LIB_MAN_DIR:@mandir@/man%=%)

libman_PRE = \
	DBE.man \
	DPMSCapable.man \
	DPMSDisable.man \
	DPMSEnable.man \
	DPMSForceLevel.man \
	DPMSGetTimeouts.man \
	DPMSGetVersion.man \
	DPMSInfo.man \
	DPMSQueryExtension.man \
	DPMSSetTimeouts.man \
	XShape.man \
	XShm.man \
	XcupGetReservedColormapEntries.man \
	XcupQueryVersion.man \
	XcupStoreColors.man \
	XdbeAllocateBackBufferName.man \
	XdbeBeginIdiom.man \
	XdbeDeallocateBackBufferName.man \
	XdbeEndIdiom.man \
	XdbeFreeVisualInfo.man \
	XdbeGetBackBufferAttributes.man \
	XdbeGetVisualInfo.man \
	XdbeQueryExtension.man \
	XdbeSwapBuffers.man \
	Xevi.man \
	Xmbuf.man

XShape_shadows = XShapeQueryExtension XShapeQueryVersion XShapeCombineRegion XShapeCombineRectangles XShapeCombineMask XShapeCombineShape XShapeOffsetShape XShapeQueryExtents XShapeSelectInput XShapeInputSelected XShapeGetRectangles

XShm_shadows = XShmQueryExtension XShmQueryVersion XShmPixmapFormat XShmAttach XShmDetach XShmCreateImage XShmPutImage XShmGetImage XShmCreatePixmap XShmGetEventBase

Xmbuf_shadows = XmbufQueryExtension XmbufGetVersion XmbufCreateBuffers XmbufDestroyBuffers XmbufDisplayBuffers XmbufGetWindowAttributes XmbufChangeWindowAttributes XmbufGetBufferAttributes XmbufChangeBufferAttributes XmbufGetScreenInfo XmbufCreateStereoWindow

Xevi_shadows = XeviQueryVersion XeviGetVisualInfo XeviQueryExtension

all_shadows = $(XShape_shadows) $(XShm_shadows) $(Xmbuf_shadows) $(Xevi_shadows)

libman_DATA = $(libman_PRE:man=@LIB_MAN_SUFFIX@) \
	      $(all_shadows:=.@LIB_MAN_SUFFIX@)

EXTRA_DIST  = $(libman_PRE)

CLEANFILES  = $(libman_DATA)

# Generate man page shadow files (Replaces InstallManPageAliases from Imake)

XShape_shadowmen = $(XShape_shadows:=.@LIB_MAN_SUFFIX@)

$(XShape_shadowmen):
	$(AM_V_GEN)echo .so man$(LIB_MAN_DIR_SUFFIX)/XShape.$(LIB_MAN_SUFFIX) > $@

XShm_shadowmen = $(XShm_shadows:=.@LIB_MAN_SUFFIX@)

$(XShm_shadowmen):
	$(AM_V_GEN)echo .so man$(LIB_MAN_DIR_SUFFIX)/XShm.$(LIB_MAN_SUFFIX) > $@

Xmbuf_shadowmen = $(Xmbuf_shadows:=.@LIB_MAN_SUFFIX@)

$(Xmbuf_shadowmen):
	$(AM_V_GEN)echo .so man$(LIB_MAN_DIR_SUFFIX)/Xmbuf.$(LIB_MAN_SUFFIX) > $@

Xevi_shadowmen = $(Xevi_shadows:=.@LIB_MAN_SUFFIX@)

$(Xevi_shadowmen):
	$(AM_V_GEN)echo .so man$(LIB_MAN_DIR_SUFFIX)/Xevi.$(LIB_MAN_SUFFIX) > $@

SUFFIXES = .$(LIB_MAN_SUFFIX) .man

# String replacements in MAN_SUBSTS now come from xorg-macros.m4 via configure
.man.$(LIB_MAN_SUFFIX):
	$(AM_V_GEN)$(SED) $(MAN_SUBSTS) < $< > $@
